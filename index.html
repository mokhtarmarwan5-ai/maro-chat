<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تطبيق مارو للدردشة الخاصة</title>
    <style>
        * { box-sizing: border-box; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; }
        body { background: #0f172a; color: #fff; margin: 0; padding: 0; display: flex; justify-content: center; align-items: center; height: 100vh; }
        .app-container { width: 100%; max-width: 450px; height: 100%; background: #1e293b; display: flex; flex-direction: column; overflow: hidden; }
        .header { background: #0f172a; padding: 15px; text-align: center; font-size: 18px; font-weight: bold; border-bottom: 1px solid #334155; }
        .screen { flex: 1; display: flex; flex-direction: column; overflow: hidden; display: none; }
        .screen.active { display: flex; }
        
        /* Auth Screen */
        .auth-box { padding: 30px; display: flex; flex-direction: column; justify-content: center; height: 100%; gap: 15px; }
        .auth-box input { padding: 12px; border-radius: 6px; border: none; background: #334155; color: white; font-size: 16px; outline: none; }
        .auth-box button { padding: 12px; background: #22c55e; color: white; border: none; border-radius: 6px; font-weight: bold; font-size: 16px; cursor: pointer; }

        /* Users List */
        .users-list { flex: 1; overflow-y: auto; padding: 10px; }
        .user-item { background: #334155; padding: 15px; margin-bottom: 10px; border-radius: 8px; cursor: pointer; display: flex; justify-content: space-between; align-items: center; }
        .user-item:active { background: #475569; }

        /* Chat Screen */
        .chat-messages { flex: 1; padding: 15px; overflow-y: auto; display: flex; flex-direction: column; gap: 10px; }
        .message { max-width: 75%; padding: 10px 14px; border-radius: 12px; word-wrap: break-word; font-size: 14px; display: flex; flex-direction: column; }
        .message.sent { background: #22c55e; color: white; align-self: flex-end; border-bottom-left-radius: 2px; }
        .message.received { background: #334155; color: white; align-self: flex-start; border-bottom-right-radius: 2px; }
        .message .sender-name { font-size: 10px; opacity: 0.8; margin-bottom: 3px; }
        
        .chat-input-area { display: flex; padding: 12px; background: #0f172a; border-top: 1px solid #334155; gap: 8px; }
        .chat-input-area input { flex: 1; padding: 10px; border: none; background: #334155; color: white; border-radius: 6px; outline: none; }
        .chat-input-area button { background: #22c55e; color: white; border: none; padding: 10px 15px; border-radius: 6px; font-weight: bold; cursor: pointer; }
        .back-btn { background: transparent; border: none; color: #38bdf8; font-size: 14px; cursor: pointer; text-align: right; padding: 10px; }
    </style>
</head>
<body>

    <div class="app-container">
        <!-- شاشة تسجيل الدخول -->
        <div id="authScreen" class="screen active">
            <div class="auth-box">
                <h2 style="text-align: center;">تسجيل دخول مارو شات</h2>
                <input type="text" id="usernameInput" placeholder="اكتب اسم المستخدم (يوزر فريد)...">
                <button onclick="login()">دخول للتطبيق</button>
            </div>
        </div>

        <!-- شاشة قائمة المستخدمين -->
        <div id="usersScreen" class="screen">
            <div class="header">قائمة الأشخاص المتاحين</div>
            <div id="usersList" class="users-list">
                <!-- سيتم تعبئة المستخدمين تلقائياً -->
            </div>
        </div>

        <!-- شاشة المحادثة الخاصّة -->
        <div id="chatScreen" class="screen">
            <button class="back-btn" onclick="goBackToUsers()">← رجوع للقائمة</button>
            <div class="header" id="chatTitle">المحادثة</div>
            <div class="chat-messages" id="messagesList"></div>
            <div class="chat-input-area">
                <input type="text" id="msgInput" placeholder="اكتب رسالتك هنا...">
                <button onclick="sendMessage()">إرسال</button>
            </div>
        </div>
    </div>

    <!-- استيراد فايربيز وسائط البيانات -->
    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/10.8.0/firebase-app.js";
        import { getDatabase, ref, set, get, push, onChildAdded, child } from "https://www.gstatic.com/firebasejs/10.8.0/firebase-database.js";

        const firebaseConfig = {
            apiKey: "AIzaSyCUs1E0Q4ZmPtCDdBkDVnnZ1maikeq1RIU",
            authDomain: "maro-store-f581b.firebaseapp.com",
            projectId: "maro-store-f581b",
            storageBucket: "maro-store-f581b.appspot.com",
            messagingSenderId: "712885860491",
            appId: "1:712885860491:web:34263ecadff4be8b0e3c8e",
            measurementId: "G-YHQK2FBMHI"
        };

        const app = initializeApp(firebaseConfig);
        const db = getDatabase(app);

        let currentUser = localStorage.getItem("maro_chat_user") || "";
        let currentChatUser = "";
        let messagesListener = null;

        window.onload = function() {
            if (currentUser) {
                showUsersScreen();
            }
        };

        window.login = async function() {
            let uInput = document.getElementById("usernameInput").value.trim();
            if (!uInput) {
                alert("برجاء إدخال اسم المستخدم");
                return;
            }

            let userRef = ref(db, 'users/' + uInput);
            let snapshot = await get(userRef);

            if (snapshot.exists()) {
                // اليوزر موجود مسبقاً، نتحقق إذا كان هو صاحب الجهاز أو شخص تاني يحاول يسرقه
                let savedOwner = localStorage.getItem("maro_chat_user");
                if (savedOwner !== uInput) {
                    alert("هذا اليوزر مستخدم بالفعل من شخص آخر، اختر يوزراً غيره!");
                    return;
                }
            } else {
                // يوزر جديد، يتم حجز الاسم في القاعدة
                await set(userRef, { username: uInput, joined: Date.now() });
            }

            currentUser = uInput;
            localStorage.setItem("maro_chat_user", currentUser);
            showUsersScreen();
        };

        function showUsersScreen() {
            document.getElementById("authScreen").classList.remove("active");
            document.getElementById("chatScreen").classList.remove("active");
            document.getElementById("usersScreen").classList.add("active");
            loadUsers();
        }

        function loadUsers() {
            let listDiv = document.getElementById("usersList");
            let usersRef = ref(db, 'users');
            
            get(usersRef).then((snapshot) => {
                listDiv.innerHTML = "";
                if (snapshot.exists()) {
                    snapshot.forEach((childSnap) => {
                        let uname = childSnap.val().username;
                        if (uname !== currentUser) {
                            let div = document.createElement("div");
                            div.className = "user-item";
                            div.innerHTML = `<span>${uname}</span> <span>💬</span>`;
                            div.onclick = () => openChat(uname);
                            listDiv.appendChild(div);
                        }
                    });
                }
            });
        }

        window.openChat = function(targetUser) {
            currentChatUser = targetUser;
            document.getElementById("chatTitle").innerText = "محادثة مع: " + targetUser;
            document.getElementById("usersScreen").classList.remove("active");
            document.getElementById("chatScreen").classList.add("active");
            
            document.getElementById("messagesList").innerHTML = "";
            
            // إنشاء معرف فريد وثابت للمحادثة بين الشخصين بغض النظر عن من يبدأها
            let chatId = [currentUser, targetUser].sort().join("_");
            let chatRef = ref(db, 'chats/' + chatId);

            onChildAdded(chatRef, (snapshot) => {
                let data = snapshot.val();
                let msgDiv = document.createElement("div");
                msgDiv.className = "message " + (data.sender === currentUser ? "sent" : "received");
                msgDiv.innerHTML = `<span class="sender-name">${data.sender}</span><span>${data.text}</span>`;
                document.getElementById("messagesList").appendChild(msgDiv);
                document.getElementById("messagesList").scrollTop = document.getElementById("messagesList").scrollHeight;
            });
        };

        window.goBackToUsers = function() {
            document.getElementById("chatScreen").classList.remove("active");
            document.getElementById("usersScreen").classList.add("active");
            loadUsers();
        };

        window.sendMessage = function() {
            let msgInput = document.getElementById("msgInput");
            if (!msgInput.value.trim() || !currentChatUser) return;

            let chatId = [currentUser, currentChatUser].sort().join("_");
            let chatRef = ref(db, 'chats/' + chatId);

            push(chatRef, {
                sender: currentUser,
                text: msgInput.value,
                timestamp: Date.now()
            });

            msgInput.value = "";
        };
    </script>
</body>
</html>
