<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>اسمك | مطوّر برمجيات</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;800&family=JetBrains+Mono:wght@400;600&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #eef1f6;
    --ink: #1b2433;
    --muted: #5b6577;
    --accent: #2f5bea;
    --panel: #1e2533;
    --panel-ink: #e6ebf5;
    --line: #cfd6e4;
  }
  * { box-sizing: border-box; }
  html { scroll-behavior: smooth; }
  body {
    margin: 0;
    font-family: "Cairo", system-ui, sans-serif;
    background: var(--bg);
    color: var(--ink);
    line-height: 1.8;
  }
  main { max-width: 860px; margin: 0 auto; padding: 56px 20px 80px; }
  h1 { font-size: clamp(2.2rem, 6vw, 3.6rem); font-weight: 800; line-height: 1.2; margin: 0 0 12px; }
  h2 { font-size: 1.5rem; margin: 64px 0 16px; }
  p { margin: 0 0 12px; max-width: 60ch; }
  .muted { color: var(--muted); }
  a { color: var(--accent); }
  a:focus-visible, button:focus-visible { outline: 3px solid var(--accent); outline-offset: 3px; }

  /* Skills: click a language to see a snippet */
  .tabs { display: flex; flex-wrap: wrap; gap: 8px; margin-bottom: 12px; }
  .tabs button {
    font: 600 0.95rem "JetBrains Mono", monospace;
    padding: 8px 16px;
    border: 1px solid var(--line);
    background: #fff;
    color: var(--ink);
    border-radius: 6px;
    cursor: pointer;
  }
  .tabs button[aria-selected="true"] { background: var(--accent); border-color: var(--accent); color: #fff; }
  pre {
    direction: ltr;
    text-align: left;
    margin: 0;
    padding: 20px;
    background: var(--panel);
    color: var(--panel-ink);
    border-radius: 8px;
    font: 400 0.95rem/1.7 "JetBrains Mono", monospace;
    overflow-x: auto;
    min-height: 150px;
  }

  /* Projects */
  .project { display: block; padding: 18px 0; border-top: 1px solid var(--line); text-decoration: none; color: inherit; }
  .project:last-child { border-bottom: 1px solid var(--line); }
  .project strong { color: var(--accent); font-size: 1.1rem; }
  .project span { display: block; color: var(--muted); }
  .project:hover strong { text-decoration: underline; }

  footer { margin-top: 64px; }
  @media (prefers-reduced-motion: reduce) { html { scroll-behavior: auto; } }
</style>
</head>
<body>
<main>
  <header>
    <h1>أهلاً، أنا اسمك</h1>
    <p class="muted">مطوّر برمجيات من أسيوط، مصر. بكتب كود للويب وبحل مشاكل بالبرمجة.</p>
    <p><a href="https://github.com/USERNAME">حسابي على GitHub</a></p>
  </header>

  <section aria-labelledby="skills-title">
    <h2 id="skills-title">المهارات</h2>
    <p class="muted">اضغط على أي لغة عشان تشوف مثال بسيط.</p>
    <div class="tabs" role="tablist" id="tabs"></div>
    <pre id="code" tabindex="0" aria-live="polite"></pre>
  </section>

  <section aria-labelledby="projects-title">
    <h2 id="projects-title">المشاريع</h2>
    <a class="project" href="https://github.com/USERNAME/project-one">
      <strong>اسم المشروع الأول</strong>
      <span>جملة واحدة تشرح المشروع بيعمل إيه. (HTML, CSS, JavaScript)</span>
    </a>
    <a class="project" href="https://github.com/USERNAME/project-two">
      <strong>اسم المشروع الثاني</strong>
      <span>جملة واحدة تشرح المشروع بيعمل إيه. (Python)</span>
    </a>
    <a class="project" href="https://github.com/USERNAME/project-three">
      <strong>اسم المشروع الثالث</strong>
      <span>جملة واحدة تشرح المشروع بيعمل إيه. (C++)</span>
    </a>
  </section>

  <footer>
    <h2>تواصل معايا</h2>
    <p><a href="mailto:you@example.com">you@example.com</a></p>
  </footer>
</main>

<script>
  const snippets = {
    "HTML": '<button id="hi">اضغط هنا</button>\n<p id="msg"></p>',
    "CSS": 'button {\n  background: #2f5bea;\n  color: white;\n  border-radius: 6px;\n  padding: 8px 16px;\n}',
    "JavaScript": 'document.getElementById("hi")\n  .addEventListener("click", () => {\n    document.getElementById("msg").textContent = "أهلاً!";\n  });',
    "Python": 'def square(n):\n    return n * n\n\nprint([square(i) for i in range(1, 6)])',
    "C++": '#include <iostream>\n\nint main() {\n    std::cout << "Hello, World!" << std::endl;\n    return 0;\n}'
  };

  const tabs = document.getElementById("tabs");
  const code = document.getElementById("code");

  function show(name) {
    code.textContent = snippets[name];
    tabs.querySelectorAll("button").forEach(b =>
      b.setAttribute("aria-selected", b.textContent === name));
  }

  Object.keys(snippets).forEach(name => {
    const b = document.createElement("button");
    b.type = "button";
    b.setAttribute("role", "tab");
    b.textContent = name;
    b.addEventListener("click", () => show(name));
    tabs.appendChild(b);
  });

  show("HTML");
</script>
</body>
</html>
