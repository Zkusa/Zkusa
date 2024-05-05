```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Yooooooooooooooooooooooooooo Animation</title>
<style>
  /* Styles for the text */
  .yoooo {
    font-size: 36px;
    font-weight: bold;
    color: #ff6600;
    position: relative;
  }
  /* Styles for the animation */
  .yoooo::after {
    content: 'o';
    position: absolute;
    top: 0;
    left: 100%;
    animation: yoooo 0.1s infinite linear;
  }
  /* Keyframes for the animation */
  @keyframes yoooo {
    0% {
      left: 100%;
    }
    100% {
      left: -100%;
    }
  }
</style>
</head>
<body>
  <!-- HTML element for the text -->
  <div class="yoooo">Y</div>
  <!-- JavaScript for duplicating the text -->
  <script>
    // Duplicate the text and adjust the number of 'o's
    const yoooo = document.querySelector('.yoooo');
    const text = yoooo.textContent.trim();
    const numO = 25; // Adjust the number of 'o's here
    yoooo.textContent = text + 'o'.repeat(numO);
  </script>
</body>
</html>




