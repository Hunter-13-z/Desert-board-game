from PIL import Image
import base64
from io import BytesIO

# Load the image
img = Image.open(' gameplay.png')
buf = BytesIO()
img.save(buf, format="PNG")
img_b64 = base64.b64encode(buf.getvalue()).decode('utf-8')

# Build README text
readme_text = f"""
README - Le Desert Interdit (Java MVC Project)

-----------------------------------------------
Overview
-----------------------------------------------
Le Desert Interdit is a Java Swing implementation of the board game
"Forbidden Desert". It follows the Model–View–Controller (MVC) architecture
and reproduces mechanics such as sandstorm movement, excavation, player roles,
water management, and artifact discovery.

-----------------------------------------------
Features
-----------------------------------------------
- 5×5 board with sand levels
- Storm meter & storm card effects
- Oasis, tunnel, and special tiles
- Artifact discovery: Navigation System, Energy Crystal,
  Hélice, Gearbox
- Multiple character roles with unique abilities
- Action system, water sharing, and equipment usage
- Graphical interface using Java Swing

-----------------------------------------------
How to Run
-----------------------------------------------
Compile:
    javac *.java

Run:
    java Le_Desert_Interdit

A window will open with the full game interface.

-----------------------------------------------
Screenshot (Base64 Embedded)
-----------------------------------------------
Below is the screenshot encoded in Base64 (PNG):

------ IMAGE BASE64 START ------
{img_b64}
------ IMAGE BASE64 END ------

-----------------------------------------------
Author
-----------------------------------------------
Hongfei ZHANG
University of Amsterdam
"""

# Save to file
output_path = "/mnt/data/README.txt"
with open(output_path, "w") as f:
    f.write(readme_text)

output_path
