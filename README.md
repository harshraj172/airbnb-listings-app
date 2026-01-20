# SF Airbnb Listings

Northeastern University - CS5610 Web Development

## Live Demo

[View the deployed app here](https://harshraj172.github.io/airbnb-listings-app/)

## About This Project

For this assignment, I built a page that loads and displays 50 Airbnb listings from San Francisco using JavaScript's fetch API and async/await. The data comes from a JSON file and gets rendered dynamically on the page.

### What the page shows:
- Listing name and description
- Price per night
- Listing thumbnail image
- Host name and photo
- Amenities (with a "show more" option)

### My creative additions:
I wanted to make this more interactive than just displaying cards, so I added:
- **Search bar** - lets you search through listings by name, description, or amenities
- **Favorites feature** - you can heart listings and they get saved to localStorage so they persist when you refresh
- **Sorting options** - sort by price low-to-high or high-to-low
- **Superhost filter** - only show listings from superhosts

## How the AJAX works

The main data loading uses fetch with async/await like we learned in class:

```javascript
async function loadData() {
    const response = await fetch('./airbnb_sf_listings_500.json');
    const data = await response.json();
    allListings = data.slice(0, 50); // grab first 50
    render(allListings);
}
```

## Tech Stack
- HTML/CSS/JavaScript (vanilla JS, no frameworks)
- Bootstrap 5 for styling
- Bootstrap Icons
- LocalStorage for favorites persistence

## Running Locally

Since this uses fetch, you need to run it from a server (wont work if you just open the html file directly due to CORS).

Using VS Code:
1. Install Live Server extension
2. Right click index.html -> Open with Live Server

Or with Python:
```bash
python -m http.server 8000
# then go to localhost:8000
```

## File Structure
```
airbnb-listings-app/
├── index.html          # everything is in here (html, css, js)
├── airbnb_sf_listings_500.json
└── README.md
```

## Deploying to GitHub Pages

1. Create a new repo on GitHub
2. Push this code to it
3. Go to Settings > Pages
4. Set source to main branch, root folder
5. Wait a minute or two and your site will be live

---

Made for CS5610 Web Development @ Northeastern

Based on the class demo: [Airbnb_Listings_demo_page](https://github.com/john-guerra/Airbnb_Listings_demo_page)
