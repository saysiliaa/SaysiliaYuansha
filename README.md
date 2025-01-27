<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Saysilia Yuansha</title>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
  <style>
    body {
      font-family: 'Cambria', Georgia, 'Times New Roman', serif;
      background-color: #f1acd7;
      color: #333;
      margin: 0;
      padding: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      text-align: center;
    }

    .container {
      background-color: white;
      border-radius: 12px;
      padding: 40px;
      box-shadow: 0 6px 10px rgba(0, 0, 0, 0.1);
      text-align: center;
      max-width: 600px;
      width: 90%;
    }

    h1 {
      color: #4CAF50;
      font-size: 2.5rem;
      cursor: pointer;
      margin-bottom: 20px;
    }

    .bio {
      font-size: 1.2em;
      color: #555;
      line-height: 1.6;
      display: none; /* Hidden initially */
    }

    .social-links {
      margin-top: 25px;
      display: flex;
      justify-content: center;
      gap: 20px;
      opacity: 0; /* Initially hidden for animation */
      transform: translateY(50px); /* Start below for upward animation */
    }

    .social-links img {
      width: 50px;
      height: 50px;
      transition: transform 0.3s ease;
    }

    .social-links img:hover {
      transform: scale(1.2);
    }
  </style>
</head>
<body>
  <div class="container">
    <h1 id="title">Saysilia's Haven</h1>
    <p class="bio" id="bio"></p>
    <div class="social-links" id="social-links">
      <a href="https://www.linkedin.com" target="_blank">
        <img src="c:/Users/DELL/Downloads/LinkedIn.png" alt="LinkedIn Logo">
      </a>
      <a href="https://www.instagram.com/saysiliaa" target="_blank">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Instagram_logo_2022.svg/2048px-Instagram_logo_2022.svg.png" alt="Instagram Logo">
      </a>
      <a href="https://www.lynk.id/saysiliayu" target="_blank">
        <img src="c:/Users/DELL/Downloads/lynk.png" alt="Lynk.id Logo">
      </a>
      <a href="https://www.tiktok.com/nnekopaws" target="_blank">
        <img src="c:/Users/DELL/Downloads/tiktok.png" alt="TikTok Logo">
      </a>
      <a href="mailto:your-saysiliayuansha@gmail.com" target="_blank">
        <img src="c:/Users/DELL/Downloads/gmaildownload.png" alt="Gmail Logo">
      </a>
    </div>
  </div>

  <script>
    const title = document.getElementById("title");
    const bio = document.getElementById("bio");
    const socialLinks = document.getElementById("social-links");
    const bioText = `Welcome to my lil cozy corner on this platform! Feel free to check out my socials to stay in the loop! Anywayy, I'm always up for meeting new fellas and vibing together. So don't be shy—let's connect!`;
    let clickCount = 0;

    // Function for typing effect
    function typeEffect(element, text, speed, callback) {
      let i = 0;
      function type() {
        if (i < text.length) {
          element.innerHTML += text.charAt(i);
          i++;
          setTimeout(type, speed);
        } else if (callback) {
          callback(); // Call the next animation
        }
      }
      type();
    }

    // Click event on title
    title.addEventListener("click", () => {
      if (clickCount === 0) {
        clickCount++;
        bio.style.display = "block";
        typeEffect(bio, bioText, 50, () => {
          // Trigger social links animation after typing finishes
          gsap.to(socialLinks, {
            opacity: 1,
            y: 0, // Move upward
            duration: 1,
            ease: "power3.out",
            onStart: () => {
              socialLinks.style.display = "flex";
            },
          });
        });
      }
    });
  </script>
</body>
</html>
