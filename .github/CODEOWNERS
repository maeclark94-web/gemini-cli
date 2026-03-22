const admin = require('firebase-admin');

// 1. Secure Initialization
// This uses the GitHub Secret we set up earlier
if (!process.env.SERVICE_ACCOUNT) {
    console.error("❌ Error: FIREBASE_SERVICE_ACCOUNT secret is missing.");
    process.exit(1);
}

const serviceAccount = JSON.parse(process.env.SERVICE_ACCOUNT);

admin.initializeApp({
  credential: admin.credential.cert(serviceAccount),
  projectId: process.env.PROJECT_ID || 'merging-banking'
});

const db = admin.firestore();

async function runDailyUpdate() {
  const docRef = db.collection('user_profiles').doc('chase_rice_main');
  const doc = await docRef.get();

  if (!doc.exists) {
    console.log("❌ Document 'chase_rice_main' not found.");
    return;
  }

  const data = doc.data();
  const currentBalance = data.total_balance || 6080333.42;
  
  // 2. The Math: 0.02% daily appreciation (approx 7.5% APY)
  const dailyGain = currentBalance * 0.0002;
  const newBalance = currentBalance + dailyGain;

  // 3. Update Firestore
  await docRef.update({
    total_balance: parseFloat(newBalance.toFixed(2)),
    last_updated: admin.firestore.Timestamp.now(),
    transaction_history: admin.firestore.FieldValue.arrayUnion({
      date: new Date().toISOString().split('T')[0],
      description: "Daily Investment Growth (Portfolio Appreciation)",
      amount: parseFloat(dailyGain.toFixed(2)),
      type: "credit"
    })
  });

  console.log(`✅ Success! New Balance for Chase Rice: $${newBalance.toFixed(2)}`);
}

runDailyUpdate().catch(err => {
  console.error("Update failed:", err);
  process.exit(1);
});