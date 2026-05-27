# 🎁 Gift Finder

An AI-powered gift recommendation engine that finds perfect gifts based on personality, interests, and budget. Uses scatter plot visualization to compare cost vs. happiness score.

## Features

- **Smart Recommendations**: AI analyzes personality type and interests to suggest personalized gift ideas
- **Real Product Search**: Finds actual products from relevant online stores (Amazon, Etsy, specialty shops, etc.)
- **Cost vs. Happiness Visualization**: Interactive scatter plot showing the tradeoff between price and satisfaction
- **Store-Aware Search**: Intelligently selects appropriate stores based on product category
- **Sidebar Details**: Click any gift to view product image, price, description, and direct purchase link
- **Budget Control**: Set your maximum budget with a simple slider
- **Responsive Design**: Works on desktop and mobile devices

## Tech Stack

- **Frontend**: HTML5, CSS3, JavaScript (vanilla)
- **Visualization**: Chart.js
- **AI API**: Groq (Mixtral 8x7b model)
- **Product Search**: Groq reasoning with real product data

## Getting Started

### Prerequisites

- A Groq API key (free at [groq.com](https://groq.com))
- A modern web browser
- Internet connection

### Installation

1. Clone or download this repository
2. Open `gift-finder.html` in your web browser
3. Enter your Groq API key when prompted

### Configuration

Edit `config.js` to change default settings:

```javascript
GROQ_API_KEY = 'your-groq-api-key-here'
GROQ_MODEL = 'mixtral-8x7b-32768' // or 'llama-3.1-70b-versatile', 'llama-3.1-8b-instant'
GROQ_TEMPERATURE = 0.7
GROQ_MAX_TOKENS = 2000
```

## Usage

### Basic Flow

1. **Enter Interests**: List hobbies, interests, and preferences (comma or line separated)
2. **Select Personality**: Choose from 7 personality types:
   - Minimalist
   - Adventurous
   - Practical
   - Artistic
   - Social
   - Tech-Savvy
   - Homebody

3. **Choose Occasion**: Birthday, Holiday, Graduation, Anniversary, Wedding, Congratulations, or Just Because
4. **Set Budget**: Use the slider to set maximum price ($10–$2000)
5. **Generate Recommendations**: Click "Find Gift Ideas"
6. **Explore Results**: 
   - View 5 gift recommendations on the scatter plot
   - Click any dot to see full product details
   - Click the "View & Buy" link to purchase

### Scatter Plot Guide

- **X-Axis**: Product cost in dollars
- **Y-Axis**: Happiness/satisfaction score (1–10)
- **Dots**: Individual gift recommendations
- **Colors**: Different colors for easy distinction
- **Hover**: See exact price and happiness score
- **Click**: Open sidebar with full product details

## File Structure

```
gift-finder/
├── README.md                 # This file
├── gift-finder.html          # Main application (HTML + CSS + JS)
├── config.js                 # Configuration and API settings
├── groq-api.js              # Groq API integration module
├── gift-recommender.js      # AI recommendation logic
├── product-search.js        # Product search and enrichment
├── chart-renderer.js        # Chart.js visualization module
└── styles/
    └── theme.css            # Additional styling (optional)
```

## API Reference

### Groq API

The application uses Groq's API for fast AI reasoning:

**Endpoint**: `https://api.groq.com/openai/v1/chat/completions`

**Models Available**:
- `mixtral-8x7b-32768` (recommended, fastest)
- `llama-3.1-70b-versatile` (most capable)
- `llama-3.1-8b-instant` (smallest, fastest)

**Rate Limits**:
- Free tier: 30 requests/minute, 14,400 requests/day
- Paid tier: Higher limits based on plan

See [Groq Docs](https://console.groq.com/docs/quickstart) for details.

## How It Works

### Step 1: Recommendation Generation

User provides interests, personality, occasion, and budget. The AI generates 5 gift recommendations with:
- Product name
- Category
- Estimated price
- Happiness score (1–10)
- Why it matches their profile
- Recommended stores to search

### Step 2: Product Enrichment

For each recommendation, the system searches for real products by:
- Identifying appropriate stores (e.g., Amazon for electronics, Etsy for handmade)
- Retrieving product URLs
- Fetching images and real prices
- Validating availability

### Step 3: Visualization

Results are plotted on an interactive scatter chart:
- Cost on X-axis
- Happiness score on Y-axis
- Click to view details

## Customization

### Change AI Model

Edit `config.js`:

```javascript
GROQ_MODEL = 'llama-3.1-70b-versatile' // More capable but slower
```

### Adjust Personality Types

Edit the `<select>` in `gift-finder.html`:

```html
<option value="custom-type">Custom Personality Type</option>
```

### Modify Budget Range

Edit the budget slider in `gift-finder.html`:

```html
<input type="range" id="budget" min="10" max="5000" value="500" step="10">
```

### Custom Stores

Add new stores to the recommendation prompt in `groq-api.js`:

```javascript
stores: ["Amazon", "Etsy", "BestBuy", "Your Custom Store"]
```

## Troubleshooting

### "Invalid API Key"
- Check that your Groq API key is correct
- Ensure the key is from [groq.com](https://groq.com), not another service
- Free tier keys work fine

### "No products found"
- The AI may not have recognized the product type
- Try more specific interests (e.g., "mechanical keyboards" vs "tech")
- Some niche products may not have real data available

### Slow responses
- Free tier has rate limits; wait a moment and try again
- Using `mixtral-8x7b-32768` is faster than `llama-3.1-70b-versatile`

### Images not loading
- Placeholder images appear if real product images aren't found
- This is normal; the purchase link still works

## Performance

- **API Response Time**: 2–5 seconds (Groq is fast)
- **Product Enrichment**: 3–10 seconds (depends on store availability)
- **Total Time**: ~10–15 seconds from submit to results

## Future Improvements

- [ ] Caching of product data to reduce API calls
- [ ] User accounts to save favorite gift lists
- [ ] Feedback loop: rate gifts after purchase to improve future recommendations
- [ ] Price comparison across multiple stores
- [ ] Integration with real shopping APIs (Amazon, Etsy, eBay)
- [ ] Gift tracking and wish lists
- [ ] Mobile app version

## License

MIT — Free to use, modify, and distribute.

## Contributing

Found a bug or have a feature request? Open an issue or submit a pull request.

## Support

For Groq API issues: [Groq Console](https://console.groq.com)
For application issues: Check the troubleshooting section above.

---

**Made with curiosity and AI.** 🚀