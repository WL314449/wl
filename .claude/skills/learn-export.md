# Skill: learn-export

Export the current learning conversation to a markdown file in the `learning-records/` directory, then push to remote repository.

## Trigger
Activated when user says: "export learning", "save learning", "导出学习", "保存学习记录", or similar phrases.

## Actions

### Step 1: Generate filename
Filename format: `YYYY-MM-DD_topic-summary.md`
- Date: use current date
- Topic: extract from the conversation subject/topic
- If no clear topic, use `general-learning`

### Step 2: Collect learning content
- Summarize the key learning points from the conversation
- Include: date, topic, core concepts covered, any code/examples, self-test answers
- Format in clean markdown with headers

### Step 3: Write file
Write to: `C:/Users/用户/24news1wl/learning-records/{filename}`

### Step 4: Git operations
Run in sequence:
```bash
git add learning-records/
git commit -m "Add learning record: {topic} ({date})"
git push origin main
```
- If branch is `master` instead of `main`, use `master`
- If remote is not set, set it first: `git remote add origin http://github.com/WL314449/wl.git`

### Step 5: Confirm
Tell the user the file was saved and pushed successfully, with the filename.

## Output style
Be concise. After pushing, say: "Done. Saved to `learning-records/{filename}` and pushed."
