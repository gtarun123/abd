index
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/tailwindcss/1.8.11/tailwind.min.css"
      integrity="sha512-KO1h5ynYuqsFuEicc7DmOQc+S9m2xiCKYlC3zcZCSEw0RGDsxcMnppRaMZnb0DdzTDPaW22ID/gAGCZ9i+RT/w=="
      crossorigin="anonymous"
    />
    <link rel="stylesheet" href="style.css" />
    <title>Password Strength Background</title>
  </head>
  <body>
    <div class="background" id="background"></div>
    <div class="bg-white rounded p-10 text-center shadow-md">
      <h1 class="text-3xl">Image Password Strength</h1>
      <p class="text-sm pt-1 text-gray-700">
        Change the password to see the effect
      </p>
      <div class="my-4 text-left">
        <label for="email" class="text-gray-900">Email:</label>
        <input
          type="text"
          name="email"
          id="email"
          class="border block w-full p-2 mt-2 rounded"
          placeholder="Enter Email"
        />
      </div>
      <div class="my-4 text-left">
        <label for="password" class="text-gray-900">Password:</label>
        <input
          type="password"
          name="password"
          id="password"
          class="border block w-full p-2 mt-2 rounded"
          placeholder="Enter Password"
        />
      </div>
      <button
        type="submit"
        class="bg-black text-white py-2 mt-4 inline-block w-full rounded"
      >
        Submit
      </button>
    </div>
    <script src="script.js"></script>
  </body>
</html>

script
const password = document.getElementById("password");
const background = document.getElementById("background");

password.addEventListener("input", (e) => {
  const input = e.target.value;
  const length = input.length;
  const blurValue = 20 - length * 2;
  background.style.filter = `blur(${blurValue}px)`;
});

css

* {
  box-sizing: border-box;
}

body {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  overflow: hidden;
  margin: 0;
}

.background {
  background: url("https://images.unsplash.com/photo-1556745757-8d76bdb6984b")
    no-repeat center center/cover;
  position: absolute;
  top: -20px;
  bottom: -20px;
  left: -20px;
  right: -20px;
  z-index: -1;
  filter: blur(20px);
}
