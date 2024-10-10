- 👋 Hi, I’m @ebbec16
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
ebbec16/ebbec16 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
from PIL import Image, ImageDraw
from PIL.features import pilinfo

images = []

width = 200
center = width // 2
color_1=(0, 0, 0)
color_2=(255,255,255)
max_radius = int(center*1.5)
step= 8

for i in range(0, max_radius, step):
    im= Image.new("RGB", (width, width), color_1)
    draw = ImageDraw.Draw(im)
    draw.ellipse((center - i, center - i, center + i, center + i), fill=color_2)
    images.append(im)

for i in range(0, max_radius, step):
    im= Image.new("RGB", (width, width), color_2)
    draw = ImageDraw.Draw(im)
    draw.ellipse((center - i, center - i, center + i, center + i), fill=color_1)
    images.append(im)

images[0].save(r"C:\Users\aybar\Pictures\Saved Pictures.gif",
               save_all=True, append_images=images[1:], optimize=False, duraiton=40, loop=0)
