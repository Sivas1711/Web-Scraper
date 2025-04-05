import requests
from bs4 import BeautifulSoup
import wikipedia

# CNN Scraper
def scrape_cnn():
    print("\n--- CNN Headlines ---")
    try:
        headers = {'User-Agent': 'Mozilla/5.0'}
        res = requests.get("https://edition.cnn.com/world", headers=headers)
        soup = BeautifulSoup(res.content, 'html.parser')
        headlines = soup.select("span.container__headline-text")
        count = 0
        for h in headlines:
            text = h.get_text(strip=True)
            if text:
                count += 1
                print(f"{count}. {text}")
            if count == 3:
                break
        if count == 0:
            print("No headlines found.")
    except Exception as e:
        print("Error scraping CNN:", e)



# Wikipedia Summary
def wiki_summary():
    topic = input("\nEnter Wikipedia topic: ")
    try:
        page = wikipedia.page(topic, auto_suggest=False)
        print(f"\n--- Wikipedia Summary: {topic} ---")
        print(page.summary[:500])
    except Exception as e:
        print("Wikipedia Error:", e)

# Main
if _name_ == "_main_":
    scrape_cnn()
    wiki_summary()
