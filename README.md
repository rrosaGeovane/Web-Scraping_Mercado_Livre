# Web-Scraping_Mercado_Livre

A Python web scraping tool that extracts notebook (laptop) information from Mercado Livre using Selenium and BeautifulSoup. This scraper specifically searches for notebooks with "16GB RAM and 1TB SSD" and saves the data to an Excel file.

## 📋 Features

- Automated search on Mercado Livre for specific notebook specifications
- Collects detailed product information including:
  - Product brand
  - Full product name (from product page)
  - Seller information
  - Price (cleaned and formatted)
  - Product rating
- Visits individual product pages to get complete details
- Saves collected data to Excel spreadsheet
- Handles pagination and navigation automatically
- Collects up to 20 products per search

## 🛠️ Technologies Used

- **Python 3.x**
- **Selenium** - Web automation and browser interaction
- **BeautifulSoup4** - HTML parsing and data extraction
- **OpenPyXL** - Excel file creation and manipulation
- **Regular Expressions (re)** - Data cleaning and formatting

## 📦 Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/mercadolibre-notebook-scraper.git
cd mercadolibre-notebook-scraper
```

2. Install required dependencies:
```bash
pip install selenium beautifulsoup4 openpyxl
```

3. Download and install ChromeDriver (compatible with your Chrome version) from [ChromeDriver Downloads](https://sites.google.com/chromium.org/driver/)

## 🚀 Usage

1. **Basic Execution:**
```bash
python scraper.py
```

2. **Customize Search Query:**
```python
# Modify the search query in the code
search_query = "notebook 16gb RAM and 1TB SSD"  # Change this to your desired search
```

3. **Adjust Number of Products:**
```python
# Change the limit in the code
if len(product_list) >= 20:  # Modify 20 to your desired number
    break
```

## 📊 Output

The script creates an Excel file named `Mercado_Livre_Products.xlsx` with the following columns:

| Brand | Name | Seller | Price | Rating |
|-------|------|--------|-------|--------|
| Dell | Dell XPS 15... | Loja Oficial Dell | 8999.99 | 4.5 |
| Lenovo | Lenovo IdeaPad... | TechStore | 5299.90 | 4.2 |

## 🔧 How It Works

1. **Initialization:** Opens Chrome browser and navigates to Mercado Livre
2. **Search:** Performs search for "notebook 16gb RAM and 1TB SSD"
3. **Collection:** For each product found:
   - Extracts basic info from search results (brand, price, rating)
   - Visits the product page to get full name and seller details
   - Navigates back to continue collecting
4. **Data Processing:** Cleans price and rating data (removes special characters, formats numbers)
5. **Export:** Saves all collected data to an Excel spreadsheet

## ⚙️ Configuration Options

```python
# Modify wait times if needed
sleep(2)  # Adjust delay between actions
sleep(5)  # Adjust initial page load wait

# Change the search query
search_query = "your custom search here"

# Modify Excel filename
wb.save("Your_Custom_Filename.xlsx")
```

## ⚠️ Important Notes

- **ChromeDriver:** Ensure ChromeDriver is installed and in your system PATH
- **Internet Speed:** Adjust `sleep()` times based on your internet connection
- **Website Changes:** Mercado Livre's HTML structure may change, requiring selector updates
- **Rate Limiting:** The script includes delays to be respectful to the server

## 🔍 Selectors Used

The script uses specific CSS classes that may need updating if Mercado Livre changes their HTML structure:

- Product wrapper: `ui-search-result__wrapper`
- Brand: `poly-component__brand`
- Title link: `poly-component__title`
- Price: `andes-money-amount__fraction`
- Rating: `polyreviews__rating`
- Product page seller: `ui-seller-data-header__title`
- Product page name: `ui-pdp-title`

## 📝 Requirements

```
selenium>=4.0.0
beautifulsoup4>=4.9.0
openpyxl>=3.0.0
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## ⚡ Disclaimer

This tool is for educational purposes only. Users are responsible for:
- Complying with Mercado Livre's terms of service
- Implementing appropriate rate limiting
- Using the data responsibly
- Checking robots.txt before scraping

The developers are not liable for any misuse of this software.

## 📧 Contact

Your Name - [@yourtwitter](https://twitter.com/yourtwitter) - email@example.com

Project Link: [https://github.com/yourusername/mercadolibre-notebook-scraper](https://github.com/yourusername/mercadolibre-notebook-scraper)

---

**Note:** Web scraping may be against the terms of service of some websites. Always check the website's robots.txt and terms of service before scraping. This code is provided as an educational example.
