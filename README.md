<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }
  body { background: #1a1a1a; display: flex; justify-content: center; align-items: center; min-height: 100vh; font-family: 'Courier New', monospace; }

  .terminal {
    width: 900px;
    background: #080808;
    border-radius: 10px;
    border: 1px solid rgba(0,255,65,0.3);
    overflow: hidden;
    box-shadow: 0 0 40px rgba(0,255,65,0.1);
  }

  .titlebar {
    background: #111;
    padding: 10px 16px;
    display: flex;
    align-items: center;
    gap: 8px;
    border-bottom: 1px solid #1a1a1a;
  }
  .btn { width: 12px; height: 12px; border-radius: 50%; }
  .red { background: #ff5f56; }
  .yellow { background: #ffbd2e; }
  .green { background: #27c93f; }
  .title-text { color: #444; font-size: 12px; margin: 0 auto; }

  .body { padding: 24px 28px 28px; min-height: 260px; }

  .line { font-size: 13px; margin-bottom: 4px; min-height: 20px; overflow: hidden; white-space: nowrap; }
  .prompt-green { color: #00FF41; }
  .prompt-dim { color: #555; }
  .white { color: #ccc; }
  .dim { color: #555; }

  .name-line {
    font-size: 64px;
    font-weight: bold;
    color: #00FF41;
    letter-spacing: 4px;
    margin: 12px 0;
    text-shadow: 0 0 10px #00FF41, 0 0 20px #00FF41, 0 0 40px #00FF4155;
    overflow: hidden;
    white-space: nowrap;
    width: 0;
  }

  .typed { overflow: hidden; white-space: nowrap; width: 0; }

  .cursor {
    display: inline-block;
    width: 9px;
    height: 15px;
    background: #00FF41;
    margin-left: 2px;
    vertical-align: middle;
    animation: blink 0.8s step-end infinite;
  }

  @keyframes blink {
    0%, 49% { opacity: 1; }
    50%, 100% { opacity: 0; }
  }

  @keyframes typing {
    from { width: 0; }
    to { width: 100%; }
  }

  @keyframes nameTyping {
    from { width: 0; }
    to { width: 860px; }
  }
</style>
</head>
<body>

<div class="terminal">
  <div class="titlebar">
    <div class="btn red"></div>
    <div class="btn yellow"></div>
    <div class="btn green"></div>
    <div class="title-text">quantum5hadow — bash — 120×40</div>
  </div>
  <div class="body">

    <div class="line typed" id="l1">
      <span class="prompt-dim">┌──(</span><span class="prompt-green">root</span><span class="prompt-dim">㉿kali)-[~]<br>└─</span><span class="prompt-green">$ </span><span class="white">cat identity.txt</span>
    </div>

    <div class="line typed" id="l2" style="color:#333">──────────────────────────────────────────────────────────</div>

    <div class="line typed" id="l3">
      <span class="dim">  role    : </span><span class="white">security engineer in the making</span>
    </div>

    <div class="line typed" id="l4">
      <span class="dim">  stack   : </span><span class="white">python · kotlin · opencv · kali · docker</span>
    </div>

    <div class="name-line" id="lname">QUANTUM5HADOW</div>

    <div class="line typed" id="l5">
      <span class="dim">  mindset : </span><span class="white">attacker brain. developer hands. always building.</span>
    </div>

    <div class="line typed" id="l6">
      <span class="dim">  status  : </span><span class="prompt-green">focused. quietly dangerous.</span>
    </div>

    <div class="line typed" id="l7">
      <span class="prompt-dim">┌──(</span><span class="prompt-green">root</span><span class="prompt-dim">㉿kali)-[~]<br>└─</span><span class="prompt-green">$ </span><span class="cursor"></span>
    </div>

  </div>
</div>

<script>
  function typeEl(el, duration, delay) {
    return new Promise(resolve => {
      setTimeout(() => {
        el.style.transition = `width ${duration}ms steps(40)`;
        el.style.width = '100%';
        setTimeout(resolve, duration);
      }, delay);
    });
  }

  function typeName(el, duration, delay) {
    return new Promise(resolve => {
      setTimeout(() => {
        el.style.transition = `width ${duration}ms steps(14)`;
        el.style.width = '860px';
        setTimeout(resolve, duration);
      }, delay);
    });
  }

  async function run() {
    await typeEl(document.getElementById('l1'), 400, 300);
    await typeEl(document.getElementById('l2'), 200, 100);
    await typeEl(document.getElementById('l3'), 500, 100);
    await typeEl(document.getElementById('l4'), 600, 100);
    await typeName(document.getElementById('lname'), 800, 200);
    await typeEl(document.getElementById('l5'), 500, 100);
    await typeEl(document.getElementById('l6'), 400, 100);
    await typeEl(document.getElementById('l7'), 300, 100);
  }

  run();
</script>
</body>
</html>
  
  
  <!-- BG -->
  <rect width="900" height="320" fill="#080808" rx="10"/>
  <rect x="1.5" y="1.5" width="897" height="317" fill="none" stroke="#00FF41" stroke-width="1" rx="9" opacity="0.3"/>

  <!-- Title bar -->
  <rect x="0" y="0" width="900" height="32" fill="#111111" rx="10"/>
  <rect x="0" y="22" width="900" height="10" fill="#111111"/>
  <circle cx="22" cy="16" r="5.5" fill="#ff5f56"/>
  <circle cx="42" cy="16" r="5.5" fill="#ffbd2e"/>
  <circle cx="62" cy="16" r="5.5" fill="#27c93f"/>
  <text x="450" y="21" text-anchor="middle" font-family="'Courier New', monospace" font-size="11" fill="#444">quantum5hadow — bash — 120×40</text>

  <!-- LINE 1: prompt + command -->
  <svg x="28" y="48" width="850" height="20" overflow="hidden">
    <rect class="t1" height="20" fill="#080808"/>
    <text y="15" font-family="'Courier New', monospace" font-size="13" fill="#00FF41">
      <tspan fill="#555">┌──(</tspan><tspan fill="#00FF41">root</tspan><tspan fill="#555">㉿kali)-[~]</tspan>
      <tspan fill="#555"> └─</tspan><tspan fill="#00FF41">$ </tspan>
      <tspan fill="#ffffff">cat identity.txt</tspan>
    </text>
  </svg>

  <!-- LINE 2 -->
  <svg x="28" y="72" width="850" height="20" overflow="hidden">
    <rect class="t2" height="20" fill="#080808"/>
    <text y="15" font-family="'Courier New', monospace" font-size="13" fill="#555">
      ──────────────────────────────────────────────────────
    </text>
  </svg>

  <!-- LINE 3 -->
  <svg x="28" y="94" width="850" height="20" overflow="hidden">
    <rect class="t3" height="20" fill="#080808"/>
    <text y="15" font-family="'Courier New', monospace" font-size="13">
      <tspan fill="#555">  role   : </tspan>
      <tspan fill="#cccccc">security engineer in the making</tspan>
    </text>
  </svg>

  <!-- LINE 4 -->
  <svg x="28" y="116" width="850" height="20" overflow="hidden">
    <rect class="t4" height="20" fill="#080808"/>
    <text y="15" font-family="'Courier New', monospace" font-size="13">
      <tspan fill="#555">  stack  : </tspan>
      <tspan fill="#cccccc">python · kotlin · opencv · kali · docker</tspan>
    </text>
  </svg>

  <!-- BIG NAME -->
  <g class="name-appear">
    <svg x="28" y="142" width="844" height="80" overflow="hidden">
      <rect class="tname" height="80" fill="#080808"/>
      <text y="68" font-family="'Courier New', monospace" font-size="72" font-weight="bold"
            fill="#00FF41" class="name-glow" letter-spacing="4">
        QUANTUM5HADOW
      </text>
    </svg>
  </g>

  <!-- LINE 5 -->
  <svg x="28" y="234" width="850" height="20" overflow="hidden">
    <rect class="t5" height="20" fill="#080808"/>
    <text y="15" font-family="'Courier New', monospace" font-size="13">
      <tspan fill="#555">  mindset: </tspan>
      <tspan fill="#cccccc">attacker brain. developer hands. always building.</tspan>
    </text>
  </svg>

  <!-- LINE 6 -->
  <svg x="28" y="256" width="850" height="20" overflow="hidden">
    <rect class="t6" height="20" fill="#080808"/>
    <text y="15" font-family="'Courier New', monospace" font-size="13">
      <tspan fill="#555">  status : </tspan>
      <tspan fill="#00FF41">focused. quietly dangerous.</tspan>
    </text>
  </svg>

  <!-- FINAL PROMPT -->
  <svg x="28" y="284" width="850" height="22" overflow="hidden">
    <rect class="tprompt" height="22" fill="#080808"/>
    <text y="16" font-family="'Courier New', monospace" font-size="13" fill="#00FF41">
      <tspan fill="#555">┌──(</tspan><tspan fill="#00FF41">root</tspan><tspan fill="#555">㉿kali)-[~]</tspan>
      <tspan fill="#555"> └─</tspan><tspan fill="#00FF41">$ </tspan>
      <tspan class="cursor" fill="#00FF41">█</tspan>
    </text>
  </svg>

</svg>

<!-- ABOUT -->


```bash
Alias    : Quantum5hadow
Role     : CS undergrad → Security + AI builder
Mindset  : attacker brain, developer hands
Status   : focused. quietly dangerous.
```

i don't chase trends. i pick something that confuses me and stay with it until it doesn't.

called myself an ultra noob once. still do. keeps me hungry.

`Tech` is my weapon. `Discipline` is my armor.

<br clear="right"/>

---

<!-- TECH STACK -->
### `> cat arsenal.txt`

**languages**

![Python](https://img.shields.io/badge/Python-0d0d0d?style=for-the-badge&logo=python&logoColor=00FF41)
![Kotlin](https://img.shields.io/badge/Kotlin-0d0d0d?style=for-the-badge&logo=kotlin&logoColor=00FF41)
![Java](https://img.shields.io/badge/Java-0d0d0d?style=for-the-badge&logo=openjdk&logoColor=00FF41)
![JavaScript](https://img.shields.io/badge/JavaScript-0d0d0d?style=for-the-badge&logo=javascript&logoColor=00FF41)
![Swift](https://img.shields.io/badge/Swift-0d0d0d?style=for-the-badge&logo=swift&logoColor=00FF41)
![Rust](https://img.shields.io/badge/Rust-0d0d0d?style=for-the-badge&logo=rust&logoColor=00FF41)
![Dart](https://img.shields.io/badge/Dart-0d0d0d?style=for-the-badge&logo=dart&logoColor=00FF41)
![Bash](https://img.shields.io/badge/Bash-0d0d0d?style=for-the-badge&logo=gnubash&logoColor=00FF41)

**vision + AI**

![OpenCV](https://img.shields.io/badge/OpenCV-0d0d0d?style=for-the-badge&logo=opencv&logoColor=00FF41)
![MediaPipe](https://img.shields.io/badge/MediaPipe-0d0d0d?style=for-the-badge&logo=google&logoColor=00FF41)
![NumPy](https://img.shields.io/badge/NumPy-0d0d0d?style=for-the-badge&logo=numpy&logoColor=00FF41)
![Flutter](https://img.shields.io/badge/Flutter-0d0d0d?style=for-the-badge&logo=flutter&logoColor=00FF41)

**security**

![Kali Linux](https://img.shields.io/badge/Kali_Linux-0d0d0d?style=for-the-badge&logo=kalilinux&logoColor=00FF41)
![Burp Suite](https://img.shields.io/badge/Burp_Suite-0d0d0d?style=for-the-badge&logo=burpsuite&logoColor=00FF41)
![Metasploit](https://img.shields.io/badge/Metasploit-0d0d0d?style=for-the-badge&logo=metasploit&logoColor=00FF41)
![Nessus](https://img.shields.io/badge/Nessus-0d0d0d?style=for-the-badge&logo=tenable&logoColor=00FF41)
![Termux](https://img.shields.io/badge/Termux-0d0d0d?style=for-the-badge&logo=gnometerminal&logoColor=00FF41)
![Linux](https://img.shields.io/badge/Linux-0d0d0d?style=for-the-badge&logo=linux&logoColor=00FF41)

**cloud + data + devops**

![AWS](https://img.shields.io/badge/AWS-0d0d0d?style=for-the-badge&logo=amazonaws&logoColor=00FF41)
![Firebase](https://img.shields.io/badge/Firebase-0d0d0d?style=for-the-badge&logo=firebase&logoColor=00FF41)
![Docker](https://img.shields.io/badge/Docker-0d0d0d?style=for-the-badge&logo=docker&logoColor=00FF41)
![Git](https://img.shields.io/badge/Git-0d0d0d?style=for-the-badge&logo=git&logoColor=00FF41)
![DynamoDB](https://img.shields.io/badge/DynamoDB-0d0d0d?style=for-the-badge&logo=amazondynamodb&logoColor=00FF41)
![Redis](https://img.shields.io/badge/Redis-0d0d0d?style=for-the-badge&logo=redis&logoColor=00FF41)
![Neo4j](https://img.shields.io/badge/Neo4j-0d0d0d?style=for-the-badge&logo=neo4j&logoColor=00FF41)
![MongoDB](https://img.shields.io/badge/MongoDB-0d0d0d?style=for-the-badge&logo=mongodb&logoColor=00FF41)

---

<!-- BOARD 1: STATS + STREAK SIDE BY SIDE -->
### `> stats --github`

<div align="center">

<img height="180" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Quantum5hadow&layout=compact&hide_border=true&bg_color=0d0d0d&title_color=00FF41&text_color=ffffff&langs_count=10" />
<img height="180" src="https://streak-stats.demolab.com?user=Quantum5hadow&theme=terminal&hide_border=true&background=0d0d0d&ring=00FF41&fire=00FF41&currStreakLabel=00FF41&sideLabels=00FF41&dates=00FF41&stroke=00FF41&currStreakNum=ffffff&sideNums=ffffff" />

</div>

---

<!-- BOARD 2: ACTIVITY GRAPH -->
### `> stats --activity`

<div align="center">

[![Activity Graph](https://github-readme-activity-graph.vercel.app/graph?username=Quantum5hadow&bg_color=0d0d0d&color=00FF41&line=00FF41&point=ffffff&area=true&hide_border=true&area_color=00FF4130)](https://github.com/ashutosh00710/github-readme-activity-graph)

</div>

---

<!-- BOARD 3: PROFILE SUMMARY CARDS -->
### `> stats --summary`

<div align="center">

[![Profile Summary](https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=Quantum5hadow&theme=github_dark)](https://github.com/vn7n24fzkq/github-profile-summary-cards)

<img width="32%" src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=Quantum5hadow&theme=github_dark" />
<img width="32%" src="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=Quantum5hadow&theme=github_dark" />
<img width="32%" src="https://github-profile-summary-cards.vercel.app/api/cards/productive-time?username=Quantum5hadow&theme=github_dark&utcOffset=5.5" />

</div>

---

</div>

---

<!-- BOARD 5: DEV JOKE -->
### `> sudo apt install humor`

<div align="center">

[![Jokes Card](https://readme-jokes.vercel.app/api?bgColor=%230d0d0d&borderColor=%2300FF41&qColor=%2300FF41&aColor=%23ffffff&textColor=%23ffffff&codeColor=%2300FF41)](https://github.com/ABSphreak/readme-jokes)

</div>

---

<!-- LEETCODE DUAL -->
### `> leetcode --both-accounts`

<div align="center">

<table border="0">
<tr>
<td align="center" width="50%">

**🆕 PixelPrince** *(active)*

[![LeetCode](https://leetcard.jacoblin.cool/PixelPrince?theme=dark&font=Fira%20Code&ext=heatmap&border=0&radius=8)](https://leetcode.com/u/PixelPrince/)

</td>
<td align="center" width="50%">

**👾 Quantumshadow** *(legacy)*

[![LeetCode](https://leetcard.jacoblin.cool/Quantumshadow?theme=dark&font=Fira%20Code&ext=heatmap&border=0&radius=8)](https://leetcode.com/u/Quantumshadow/)

</td>
</tr>
</table>

> two accounts. one grind. `discipline > motivation.`

</div>

---



<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Quantum5hadow/Quantum5hadow/output/github-contribution-grid-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Quantum5hadow/Quantum5hadow/output/github-contribution-grid-snake.svg" />
  <img alt="pacman eating commits" src="https://raw.githubusercontent.com/Quantum5hadow/Quantum5hadow/output/github-contribution-grid-snake-dark.svg" />
</picture>

</div>

---


<div align="center">

[![Readme Quotes](https://quotes-github-readme.vercel.app/api?type=horizontal&theme=dark&quote=The+quieter+you+become%2C+the+more+you+are+able+to+hear.&author=Kali+Linux)](https://github.com/piyushsuthar/github-readme-quotes)

</div>

---


<div align="center">

```
currently:  building things slightly too ambitious for where i am
motive:     i work for nobody. that's not sad. that's a choice.
mystery:    got a wizard profile somewhere. maybe you'll find it.
```

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:00FF41,100:000000&height=120&section=footer&animation=twinkling" />

</div>
