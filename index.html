<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تطبيق مراسلة لحظي - مارو</title>
    <style>
        * { box-sizing: border-box; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; }
        body { background: #0f172a; color: #fff; margin: 0; padding: 20px; display: flex; justify-content: center; align-items: center; height: 100vh; }
        .chat-container { width: 100%; max-width: 450px; background: #1e293b; border-radius: 12px; display: flex; flex-direction: column; height: 85vh; box-shadow: 0 10px 25px rgba(0,0,0,0.5); overflow: hidden; }
        .chat-header { background: #0f172a; padding: 15px; text-align: center; font-size: 18px; font-weight: bold; border-bottom: 1px solid #334155; }
        .chat-messages { flex: 1; padding: 15px; overflow-y: auto; display: flex; flex-direction: column; gap: 10px; }
        .message { background: #334155; padding: 10px 14px; border-radius: 8px; max-width: 75%; word-wrap: break-word; }
        .message .sender { font-size: 11px; color: #cbd5e1; margin-bottom: 3px; display: block; }
        .chat-input-area { display: flex; padding: 12px; background: #0f172a; border-top: 1px solid #334155; gap: 8px; }
        input, button { padding: 10px 14px; border: none; border-radius: 6px; font-size: 14px; outline: none; }
        input#name-input { width: 30%; background: #334155; color: white; }
        input#msg-input { flex: 1; background: #334155; color: white; }
        button { background: #22c55e; color: white; font-weight: bold; cursor: pointer; }
        button:active { transform: scale(0.95); }
    </style>
</head>
<body>

    <div class="chat-container">
        <div class="chat-header">غرفة الدردشة الفورية 💬</div>
        <div class="chat-messages" id="messagesList"></div>
        <div class="chat-input-area">
            <input type="text" id="name-input" placeholder="اسمك..." value="مارو">
            <input type="text" id="msg-input" placeholder="اكتب رسالتك هنا...">
            <button onclick="sendMessage()">إرسال</button>
        </div>
    </div>

    <!-- استيراد فايربيز SDKs -->
    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/10.8.0/firebase-app.js";
        import { getDatabase, ref, push, onChildAdded } from "https://www.gstatic.com/firebasejs/10.8.0/firebase-database.js";

        // إعدادات المشروع الخاصة بك
        const firebaseConfig = {
            apiKey: "AIzaSyCUSiE0Q4ZmPtCOdBkDvNnZ1maikeqiRIU",
            authDomain: "maro-store-f581b.firebaseapp.com",
            projectId: "maro-store-f581b",
            storageBucket: "maro-store-f581b.firebasestorage.app",
            messagingSenderId: "712885860491",
            appId: "1:712885860491:web:34263ecadff4be8b0e3c8e",
            measurementId: "G-YHQK2PBNH1"
        };

        // تهيئة فايربيز وقاعدة البيانات
        const app = initializeApp(firebaseConfig);
        const db = getDatabase(app);
        const messagesRef = ref(db, 'chats');

        window.sendMessage = function() {
            const nameInput = document.getElementById('name-input');
            const msgInput = document.getElementById('msg-input');

            if(msgInput.value.trim() === "") return;

            // إرسال الرسالة لقاعدة البيانات
            push(messagesRef, {
                sender: nameInput.value || "مستخدم",
                text: msgInput.value,
                timestamp: Date.now()
            });

            msgInput.value = "";
        }

        // استقبال الرسائل لحظياً بدون تحديث
        const messagesList = document.getElementById('messagesList');
        onChildAdded(messagesRef, (snapshot) => {
            const data = snapshot.val();
            const msgDiv = document.createElement('div');
            msgDiv.className = 'message';
            msgDiv.innerHTML = `<span class="sender">${data.sender}</span>${data.text}`;
            messagesList.appendChild(msgDiv);
            messagesList.scrollTop = messagesList.scrollHeight; // نزول تلقائي لأسفل الشات
        });
    </script>

</body>
</html>

