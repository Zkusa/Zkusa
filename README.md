<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Animated Text</title>
  <style>
    /* Styles for the text */
    .hello {
      font-size: 36px;
      font-weight: bold;
      white-space: nowrap; /* Prevents line breaks */
    }
  </style>
</head>
<body>
  <!-- HTML element for the text -->
  <div class="hello" id="helloText">
    <span>Y</span> <span>o</span> <span>o</span> <span>o</span> <span>o</span> <span>o</span> <span>o</span> <span>o</span> <span>o</span> <span>o</span> <span>o</span> <span>o</span> <span>o</span> <span>o</span> <span>o</span> <span>o</span> 
  </div>

  <script>
    // Function to generate shades of a color
    function generateShades(color, count) {
      const colors = [];
      for (let i = 0; i < count; i++) {
        const shade = `#${Math.floor(color[0] * (1 - i / (count - 1))).toString(16).padStart(2, '0')}${Math.floor(color[1] * (1 - i / (count - 1))).toString(16).padStart(2, '0')}${Math.floor(color[2] * (1 - i / (count - 1))).toString(16).padStart(2, '0')}`;
        colors.push(shade);
      }
      return colors;
    }

    // Generate shades of colors
    const baseColors = [[255, 0, 0], [0, 255, 0], [0, 0, 255], [255, 0, 255], [255, 255, 0]];
    const colors = baseColors.flatMap(color => generateShades(color, 16));

    // Function to animate the text
    function animateText() {
      const letters = document.querySelectorAll('.hello span');
      
      letters.forEach((letter, index) => {
        letter.style.opacity = 0;
        
        setTimeout(() => {
          letter.style.opacity = 1;
          letter.style.color = colors[index];
        }, 100 * index);
      });
      
      // Call the function recursively after all letters have faded in
      setTimeout(() => {
        letters.forEach((letter, index) => {
          letter.style.opacity = 0;
        });
        setTimeout(animateText, 1600); // Wait for 1.6 seconds before starting the next loop
      }, 1600); // Wait for 1.6 seconds before starting the next loop
    }
    
    // Start the animation
    animateText();
  </script>
</body>
</html>
