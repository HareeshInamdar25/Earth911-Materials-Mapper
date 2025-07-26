# Earth911-Materials-Mapper

Certainly! Here’s a human-written README file suitable for your GitHub project based on the Python code and workflow described earlier.

# Earth911 Materials Mapper

A Python script that automates the extraction and structuring of recycling facility data from [Earth911](https://search.earth911.com/).  
This tool scrapes recycling locations within a specified ZIP code and matches their accepted materials to standardized categories using OpenAI’s GPT Language Model.


## ✨ Features

- 🚀 **Automated scraping** of facility cards via Selenium WebDriver.
- 🤖 **LLM-powered classification**: Maps raw materials text from the web into clean, structured categories using OpenAI GPT-3.5.
- 🗂️ **Extensible categories:** Easily add or modify the groups of materials in a single config.
- 🛡️ **Edge case handling:** Deals with messy web data and incomplete fields.

## 📦 Output Example

```json
[
  {
    "business_name": "Best Buy - 5th Ave",
    "last_update_date": "2024-04-22",
    "street_address": "529 5th Ave, New York, NY 10017",
    "materials_category": ["Electronics", "Batteries"],
    "materials_accepted": ["Computers, Laptops, Tablets", "Cell Phones, Smartphones", "Lithium-ion Batteries"]
  },
  ...
]
```

## 🛠 Requirements

- Python 3.8+
- [OpenAI API Key](https://platform.openai.com/)
- Chrome Browser (Selenium uses ChromeDriver)

Install dependencies:
```bash
pip install selenium openai beautifulsoup4 webdriver-manager
```

## 🚦 Usage

1. **Set your OpenAI API Key:**  
   Open the script and update `OPENAI_API_KEY` with your key.

2. **Run the script**
   ```bash
   python earth911_scraper.py
   ```

3. **Review Output:**  
   Results are saved as `scraped_earth911.json`.

## 👩‍💻 How It Works

1. **Web Scraping**:   
   The script launches a Chrome browser, searches Earth911 for facilities in your specified ZIP code, and retrieves their raw data.

2. **Classifying Materials:**  
   Facility material listings are mapped into standardized categories using a prompt-powered OpenAI model, making the data easy to compare, filter, or analyze.

3. **Output:**  
   Everything is saved in clean, readable JSON.

## 🧩 Customization

- **Change Categories:**  
  Modify the `CATEGORIES` dictionary in the script to adjust types of materials recognized.
- **Increase Listings:**  
  Edit how many facility cards to parse in the script’s loop (`results[:3]`).

## ⚠️ Caveats

- **API Cost:** Each facility classification is an LLM API call. For large datasets, check your OpenAI usage.
- **Browser Automation:**  
   This script uses Selenium to load dynamic content. It won’t work on servers where you can’t run a browser.
- **Website Structure:**  
   If Earth911 updates its layout, selectors may need adjustment.

## 🥇 Why use this?

- Quickly build centralized, standardized recycling data.
- Skip tedious copy-pasting and manual categorizing of materials.
- Source for data science or sustainability research projects.

## 🙋‍♂️ Contributing

PRs and issues are welcome!  
If you build a new prompt, support more categories, or want to discuss alternate LLMs/workflows, open an issue.

