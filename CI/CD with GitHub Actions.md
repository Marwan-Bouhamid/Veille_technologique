---
marp: true
theme: default
paginate: true
size: 16:9
title: CI/CD with GitHub Actions
description: Automating code quality with GitHub Actions
footer: "CI/CD with GitHub Actions · Marwan Bouhamid · SOLICODE Tanger"
style: |
  section {
    background: #0b1220;
    color: #eef4ff;
    font-family: "Aptos", "Segoe UI", sans-serif;
    padding: 52px 68px;
  }
  h1, h2 {
    color: #f8fbff;
    letter-spacing: -0.03em;
  }
  h1 { font-size: 2.25em; }
  h2 { font-size: 1.65em; }
  strong { color: #57d6c3; }
  a { color: #57d6c3; }
  ul { line-height: 1.55; }
  li::marker { color: #57d6c3; }
  section.lead {
    background: linear-gradient(135deg, #0b1220 10%, #12334b 100%);
    justify-content: center;
  }
  section.lead h1 {
    color: #57d6c3;
    font-size: 2.7em;
    max-width: 760px;
  }
  section.lead h2 {
    color: #d3e2f2;
    font-size: 1.35em;
    font-weight: 400;
  }
  section.lead p { color: #a9bfd2; }
  section.center { text-align: center; }
  section.center ul {
    display: inline-block;
    text-align: left;
  }
  pre {
    background: #111d2d;
    border: 1px solid #263a50;
    border-radius: 12px;
    font-size: 0.68em;
    line-height: 1.2;
    padding: 12px 20px;
  }
  pre code, pre code * { color: #e6edf7 !important; }
  pre code .hljs-attr,
  pre code .hljs-attribute,
  pre code .hljs-keyword { color: #7dd3fc !important; }
  pre code .hljs-string,
  pre code .hljs-meta .hljs-string { color: #a7f3d0 !important; }
  pre code .hljs-literal,
  pre code .hljs-number { color: #f9a8d4 !important; }
  pre code .hljs-punctuation,
  pre code .hljs-bullet { color: #c4b5fd !important; }
  section.workflow { padding-bottom: 56px; }
  section.workflow h2 { margin-bottom: 0.35em; }
  section.workflow h3 { margin: 0.55em 0 0.5em; font-size: 1.05em; }
  .workflow-results {
    display: flex;
    gap: 20px;
  }
  .workflow-result {
    flex: 1;
    display: flex;
    align-items: center;
    gap: 12px;
    background: #111d2d;
    border: 1px solid #263a50;
    border-radius: 10px;
    padding: 10px 16px;
    font-size: 0.86em;
  }
  .workflow-result .status-icon {
    font-size: 1.5em;
    font-weight: 700;
  }
  .workflow-result.passed .status-icon { color: #4ade80; }
  .workflow-result.failed .status-icon { color: #fb7185; }
  footer { color: #829ab0; font-size: 0.65em; }
---

<!-- _class: lead -->

# CI/CD with GitHub Actions

## Automating Code Quality

**Marwan Bouhamid** · SOLICODE Tanger

M3: Assurer la qualité · M4: Déployer une solution logicielle

---

## 1 · What is CI/CD?

- **Continuous Integration (CI):** build and test code automatically on every push.
- **Continuous Delivery / Deployment (CD):** make validated code ready for release, or release it automatically.
- **The goal:** catch bugs early, release faster, and collaborate better.

---

## 2 · The problem

- Manual testing before every push takes time.
- Broken code and syntax errors can reach the main branch.
- Teammates may pull broken code and lose time.
- Quality checks depend on every developer remembering to run them.

---

## 3 · The solution: GitHub Actions

- A **workflow** is an automated process defined in a YAML file under `.github/workflows/`.
- A **trigger** is an event that starts the workflow, such as `push` or `pull_request`.
- A **job** is a group of steps running on a clean virtual machine.
- **Steps** can check out code, install dependencies, and run tests.

---

<!-- _class: workflow -->

## 4 · Demo: a simple PHP workflow

```yaml
name: CI

on: [push, pull_request]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: shivammathur/setup-php@v2
        with:
          php-version: '8.2'
      - run: composer install
      - run: vendor/bin/phpunit
```

### Results appear directly in the pull request

<div class="workflow-results">
  <div class="workflow-result passed"><span class="status-icon">✓</span><span><strong>Tests passed</strong><br>Green check</span></div>
  <div class="workflow-result failed"><span class="status-icon">✕</span><span><strong>Tests failed</strong><br>Red cross</span></div>
</div>

---


## 5 · Conclusion

- Faster feedback on every push
- Fewer bugs reaching the main branch
- Smoother team collaboration

# Thank you!

### Questions?

[Source presentation](https://docs.google.com/presentation/d/1EAPUjt-JtUNLyJ-fCC9t0ov1Eds-k7W55AAeyagMd8Q/edit?usp=sharing)
