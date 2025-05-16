# Konichiwa 👋

<div align="center">
<img hight="300" width="700" alt="GIF" align="center" src="https://i.pinimg.com/originals/4a/59/04/4a5904db82b19b2965026a04b073503f.gif">
</div>

</br>
</br>
</br>


# About ME 💬 :

### - I'm 17 years  old coding learning Enthusiast from India.

<img hight="400" width="500" alt="GIF" align="right" src="https://giffiles.alphacoders.com/221/221578.gif">

### - Learning :
- ✨ whatsapp bot development 
- ✨ AI prompt

### - Hobbies : 
- ✨ Solving rubiks cube
- ✨ Watching Anime
- ✨ calisthenics 
- ✨ Badminton

</br>
</br>
</br>

## Activities

<img align="left" width="480" alt="metrics" src="/github-metrics.svg">
<img align="right" alt="count" src="https://count.getloli.com/get/@:usernametheme=rule34">




## 🌐 Socials:
[![X](https://img.shields.io/badge/X-black.svg?logo=X&logoColor=white)](https://x.com/https://x.com/PiyushGupt60087?t=lVfVWREZko-uHo6v8I_1Lw&s=09) [![YouTube](https://img.shields.io/badge/YouTube-%23FF0000.svg?logo=YouTube&logoColor=white)](https://youtube.com/@https://youtube.com/@phoenixfury_editz0001) 

# 💻 Tech Stack:
![C++](https://img.shields.io/badge/c++-%2300599C.svg?style=for-the-badge&logo=c%2B%2B&logoColor=white) ![Render](https://img.shields.io/badge/Render-%46E3B7.svg?style=for-the-badge&logo=render&logoColor=white) ![Cloudflare](https://img.shields.io/badge/Cloudflare-F38020?style=for-the-badge&logo=Cloudflare&logoColor=white) ![NodeJS](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white) ![WordPress](https://img.shields.io/badge/WordPress-%23117AC9.svg?style=for-the-badge&logo=WordPress&logoColor=white) ![Adobe Lightroom](https://img.shields.io/badge/Adobe%20Lightroom-31A8FF.svg?style=for-the-badge&logo=Adobe%20Lightroom&logoColor=white) ![Adobe Fonts](https://img.shields.io/badge/Adobe%20Fonts-000B1D.svg?style=for-the-badge&logo=Adobe%20Fonts&logoColor=white) ![Adobe](https://img.shields.io/badge/adobe-%23FF0000.svg?style=for-the-badge&logo=adobe&logoColor=white) ![Adobe Acrobat Reader](https://img.shields.io/badge/Adobe%20Acrobat%20Reader-EC1C24.svg?style=for-the-badge&logo=Adobe%20Acrobat%20Reader&logoColor=white) ![Canva](https://img.shields.io/badge/Canva-%2300C4CC.svg?style=for-the-badge&logo=Canva&logoColor=white) ![Git](https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white) ![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white) ![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
# 📊 GitHub Stats:
![](https://github-readme-stats.vercel.app/api?username=PhoenixFury0000&theme=dark&hide_border=false&include_all_commits=false&count_private=false)<br/>
![](https://nirzak-streak-stats.vercel.app/?user=PhoenixFury0000&theme=dark&hide_border=false)<br/>
![](https://github-readme-stats.vercel.app/api/top-langs/?username=PhoenixFury0000&theme=dark&hide_border=false&include_all_commits=false&count_private=false&layout=compact)





on:

  # Schedule the workflow to run daily at midnight UTC

  schedule:

    - cron: "0 0 * * *"



  # Allow manual triggering of the workflow

  workflow_dispatch:



  # Trigger the workflow on pushes to the main branch

  push:

    branches:

      - main



jobs:

  generate:

    runs-on: ubuntu-latest

    timeout-minutes: 10



    steps:

      # Step 1: Checkout the repository

      - name: Checkout Repository

        uses: actions/checkout@v3



      # Step 2: Generate the snake animations

      - name: Generate GitHub Contributions Snake Animations

        uses: Platane/snk@v3

        with:

          # GitHub username to generate the animation for

          github_user_name: ${{ github.repository_owner }}



          # Define the output files and their configurations

          outputs: |

            dist/github-snake.svg

            dist/github-snake-dark.svg?palette=github-dark

            dist/ocean.gif?color_snake=orange&color_dots=#bfd6f6,#8dbdff,#64a1f4,#4b91f1,#3c7dd9

        env:

          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}



      # Step 3: Deploy the generated files to the 'output' branch

      - name: Deploy to Output Branch

        uses: peaceiris/actions-gh-pages@v3

        with:

          github_token: ${{ secrets.GITHUB_TOKEN }}

          publish_dir: ./dist

          publish_branch: output

          # Optionally, you can set a custom commit message

          commit_message: "Update snake animation [skip ci]"


