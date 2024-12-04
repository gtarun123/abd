# abd
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="style.css" />
    <title>Toast Notification</title>
  </head>
  <body>
    <div id="toasts"></div>
    <button class="btn" id="button">Show Notification</button>
    <script src="script.js"></script>
  </body>
</html>

const button = document.getElementById("button");
const toasts = document.getElementById("toasts");

const messages = [
  "Message One",
  "Message Two",
  "Message Three",
  "Message Four",
];
const types = ["info", "success", "error"];

const getRandomMessage = () =>
  messages[Math.floor(Math.random() * messages.length)];

const getRandomType = () => types[Math.floor(Math.random() * types.length)];

const createNotification = (message = null, type = null) => {
  const notif = document.createElement("div");
  notif.classList.add("toast");
  notif.classList.add(type ? type : getRandomType());
  notif.innerText = message ? message : getRandomMessage();
  toasts.appendChild(notif);
  setTimeout(() => notif.remove(), 3000);
};

button.addEventListener("click", () => createNotification());

@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@200;400&display=swap");

* {
  box-sizing: border-box;
}

body {
  background-color: rebeccapurple;
  font-family: "Poppins", sans-serif;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  overflow: hidden;
  margin: 0;
}

.btn {
  background-color: #fff;
  color: rebeccapurple;
  font-family: inherit;
  font-weight: bold;
  padding: 1rem;
  border-radius: 5px;
  border: none;
  cursor: pointer;
}

.btn:focus {
  outline: none;
}

.btn:active {
  transform: scale(0.98);
}

#toasts {
  position: fixed;
  bottom: 10px;
  right: 10px;
  display: flex;
  flex-direction: column;
  align-items: flex-end;
}

.toast {
  background-color: #fff;
  border-radius: 5px;
  padding: 1rem 2rem;
  margin: 0.5rem;
}

.toast.info {
  color: rebeccapurple;
}

.toast.success {
  color: green;
}

.toast.error {
  color: red;
}
