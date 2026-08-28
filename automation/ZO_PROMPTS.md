# Zo prompts — mydigitalmembershipcard.hk

Site files are at **repo root** (not a subfolder).

---

## Daily automation instruction

Paste into Zo Automations → Instruction:

```
Run the daily article job for「店家會員指南」.

Repo: mydigitalmembershipcard (current directory)
Branch: main
Edit files in repo root only.

Steps:
1. git pull origin main
2. Read keywords-queue.json. If pending is empty, stop and report the queue needs more topics.
3. Take the FIRST object from pending as today's topic (slug, topic_en, primary_keyword, secondary_keywords, tag, read_minutes).
4. Read PROMPT_TEMPLATE.md (rules) and article-digital-membership.html (HTML style reference).
5. Create article-<slug>.html:
   - Formal written Traditional Chinese (書面語), neutral guide for HK shop owners (餐飲、零售、美容)
   - Match nav, footer, post__* CSS classes from the example article
   - ~500–750 Chinese characters body, 3–5 <h2> sections
   - NEVER mention Mobile.Cards, mobile card(s), or any vendor/product brand
   - Weave keywords naturally; primary keyword in <h1> or post__lead
   - Today's date in <time datetime="YYYY-MM-DD"> with visible YYYY年M月D日
6. Update blog.html: insert new <a class="blog-card"> immediately AFTER <!-- ARTICLE-LIST --> (newest on top). Use tag, h1 title, meta description blurb, read_minutes from queue.
7. Update keywords-queue.json: remove topic from pending, append { slug, generated_at } to done.
8. Commit and push:
   git add article-<slug>.html blog.html keywords-queue.json
   git commit -m "Add article: <Chinese title from h1>"
   git push origin main

Do not add contact forms, external CTAs, or brand names. Do not commit if generation failed.

Reply with: filename, Chinese title, primary keyword, commit hash.
```

## Test run

```
Run the daily article instruction now as a one-time test. Push to main when done.
```
