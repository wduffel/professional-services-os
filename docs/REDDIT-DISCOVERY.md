# Reddit Customer Discovery — Pain Point Scraping Guide

## Why Reddit?

Reddit communities are FULL of real complaints:
- r/LawSchool — law students hating on their software
- r/Barexam — bar exam candidates frustrated with tools
- r/Lawyers — attorneys complaining about practice management
- r/Accounting — accountants hating their software
- r/FinancialPlanning — advisors frustrated with CRMs

---

## TWO APPROACHES

### Approach A: Manual Search (No Code Needed) — START HERE

**Step 1: Search these subreddits manually**

| Subreddit | Search Term | What You'll Find |
|-----------|-------------|------------------|
| r/LawSchool | "worst tool" "hate" "frustrated" | What students hate |
| r/Lawyers | "software" "Clio" "hate" | Attorney complaints |
| r/Barexam | "tool" "study aid" "help" | Bar prep frustrations |
| r/Accounting | "practice management" "Karbon" "hate" | Accountant complaints |
| r/FinancialPlanning | "CRM" "Wealthbox" "frustrated" | Advisor complaints |
| r/InsuranceAgent | "AMS" "agency software" "worst" | Insurance complaints |

**Step 2: Search keywords**

Try searching in each sub:
- "[Software name] complaints"
- "worst [industry] software"
- "looking for [tool] alternatives"
- "[product] vs" threads
- "has anyone used X?" (usually complaints in comments)

**Step 3: Copy-paste into a doc**

Make a spreadsheet with:
```
| Source | Post Title | Complaint | Feature Gap |
|--------|------------|-----------|-------------|
| r/Lawyers | "Clio is terrible for..." | Can't do X | Need feature Y |
```

---

### Approach B: API-Based (For Automation Later)

#### Option 1: Use a simple script

```python
import praw
import pandas as pd
from datetime import datetime, timedelta

# Set up Reddit API (get credentials at reddit.com/prefs/apps)
reddit = praw.Reddit(
    client_id="YOUR_CLIENT_ID",
    client_secret="YOUR_SECRET",
    user_agent="pain_research_1.0"
)

# Subreddits to search
subreddits = ["lawschool", "lawyers", "barexam", "FinancialPlanning", "InsuranceAgent"]

# Search terms per industry
search_queries = [
    ("legal", "practice management software", "hate", "worst", "frustrated"),
    ("accounting", "practice management", "Karbon", "hate", "terrible"),
    ("investments", "CRM", "Wealthbox", "hate", "frustrated"),
    ("insurance", "agency management", "hate", "worst", "terrible")
]

results = []

for sub in subreddits:
    print(f"Scraping r/{sub}...")
    subreddit = reddit.subreddit(sub)
    
    # Get recent posts
    for post in subreddit.new(limit=100):
        # Check if post contains complaint keywords
        post_lower = post.title.lower() + post.selftext.lower()
        
        complaint_keywords = ["hate", "worst", "terrible", "frustrated", "annoying", 
                            "don't like", "sucks", "broken", "bug", "issue"]
        
        if any(kw in post_lower for kw in complaint_keywords):
            results.append({
                "subreddit": sub,
                "title": post.title,
                "url": post.url,
                "score": post.score,
                "date": datetime.fromtimestamp(post.created_utc)
            })

# Save to CSV
df = pd.DataFrame(results)
df.to_csv("reddit_complaints.csv", index=False)
print(f"Found {len(results)} complaint posts")
```

#### Option 2: Use existing tools

| Tool | What It Does | Cost |
|------|--------------|------|
| **Reddit Comment Search** | Search comments (not posts) | Free tier |
| **Publish0x** | Track keywords | Free tier |
| **Brandwatch** | Enterprise social listening | $$$ |
| **Mention** | Brand monitoring | $100+/mo |
| **PagerDuty** (for Reddit) | Real-time alerts | Free |

---

## What to Look For (Categorization)

### When reading complaints, categorize by:

| Category | Example |
|----------|---------|
| **Missing Feature** | "Can't track time in Clio" |
| **Bad UX** | "This interface is so confusing" |
| **Integration** | "Doesn't sync with QuickBooks" |
| **Pricing** | "They doubled the price for no reason" |
| **Performance** | "App is so slow" |
| **Bugs** | "Invoice won't generate" |
| **Support** | "Can't reach support" |
| **Complexity** | "Too complicated for small firm" |

---

## Action Plan

### Today (Manual):

1. Search r/LawSchool + r/Lawyers → Note complaints → Document gaps
2. Search r/Barexam → Note what students want
3. Search r/FinancialPlanning → Note what advisors want
4. Search r/InsuranceAgent → Note what agents want

### This Week:

1. Compile all into one "Pain Points" doc
2. Identify top 3 complaints per vertical
3. Cross-reference with MVP feature list
4. Adjust MVP to match REAL needs

---

## Example Output Format

```
PAIN POINT RESEARCH — [Date]

LEGAL VERTICAL:
| Complaint Source | Quote | Root Problem | Our Solution |
|------------------|-------|--------------|--------------|
| r/Lawyers | "Clio billing is a nightmare" | Time → Invoice is clunky | Build streamlined time-to-invoice |
| r/LawSchool | "No one explains practice mgmt" | No training | Include in-app education |

ACCOUNTING VERTICAL:
...

INVESTMENTS VERTICAL:
...

INSURANCE VERTICAL:
...
```

---

## KEY INSIGHT

Don't build "theoretical better product."

Build exactly what people are complaining about right now.

Every complaint = potential feature to build.

---

*This guide helps you validate the MVP with real-world pain points rather than assumptions.*