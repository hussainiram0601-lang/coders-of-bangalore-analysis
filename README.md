# Coders of Bangalore: Instagram Follower Data Analysis

An exploratory data analysis and text parsing pipeline built in Python to extract, clean, and structure Instagram follower metadata into JSON format.

---

## 📌 Story Background

> You ask Sam Altman for $2.2 Billion in funding. He laughs, asks where you live, and gives you a 24-hour challenge:
> 
> **"Collect raw Instagram data of all OpenAI followers and answer key analytical questions."**
> 
> You hire Vijyalaxmi Iyer (Hebbal) and Sam Chandra (HSR Layout) and set up a war-room at **Rameshwaram Cafe, Indiranagar** to crunch the data.

---

## 🎯 Questions to Answer

- 📈 **Maximum Posts:** Who among the followers has published the highest number of posts?
- 👥 **Maximum Followers:** Who commands the largest audience?
- 🔗 **Maximum Following:** Who follows the highest number of accounts?
- 🏷️ **Category Breakdown:** How many distinct page types (Digital Creator, Nonprofit, Media, Investor, etc.) exist across the user base?

---

## 📂 Repository Structure

```text
.
├── coders-of-bangalore.ipynb  # Main Jupyter Notebook containing data parsing logic
├── initialdata.txt             # Initial raw unstructured Instagram profile dump
├── finaldata.txt               # Expanded raw dataset covering Bangalore tech profiles
└── README.md                   # Project documentation
```

---

## 🛠️ Data Pipeline & Architecture

1. **Ingestion:** Reads raw multiline text files containing scraped Instagram metadata.
2. **Chunking:** Dynamically splits data streams using double newline delimiters (`\n\n`).
3. **Parsing (`parse_chunk`):** Custom parser that isolates target attributes:
   - `username`
   - `no_of_posts`
   - `no_of_followers`
   - `no_of_following`
   - `name`
   - `type_of_page` (e.g., Digital Creator, Community, Entrepreneur)
   - `bio`
4. **Serialization:** Exports structured Python dictionaries into clean, indented JSON format (`json.dumps`).

---

## 🚀 How to Run

1. Clone this repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/coders-of-bangalore.git
   cd coders-of-bangalore
   ```

2. Open the notebook in Jupyter Notebook or JupyterLab:
   ```bash
   jupyter notebook coders-of-bangalore.ipynb
   ```

3. Execute all cells to run the parsing pipeline and view the generated JSON structure.

---

## 💻 Sample Output Format

```json
[
    {
        "username": "bangalore_tech_bro",
        "no_of_posts": "402 posts",
        "no_of_followers": "12.5K followers",
        "no_of_following": "890 following",
        "name": "Rahul | HSR Hustler",
        "type_of_page": "Entrepreneur",
        "bio": "🚀 Building the next Unicorn in Fintech\n☕ 3rd Wave Coffee addict\n💻 Python | React | AI\n📍 HSR Layout, BLR\nlinktr.ee/rahulbuilds"
    }
]
```
