/**
 * Configuration for Gift Finder
 * Update these settings to customize behavior
 */

const CONFIG = {
  // Groq API Configuration
  API: {
    // Get your free API key from https://console.groq.com
    KEY: '', // Leave empty to prompt user, or paste your key here
    
    // Groq API endpoint (do not change)
    ENDPOINT: 'https://api.groq.com/openai/v1/chat/completions',
    
    // Model selection
    // Options: 'mixtral-8x7b-32768' (fastest), 'llama-3.1-70b-versatile' (most capable), 'llama-3.1-8b-instant' (smallest)
    MODEL: 'mixtral-8x7b-32768',
    
    // Model temperature (0-2)
    // Lower = more deterministic, Higher = more creative
    TEMPERATURE: 0.7,
    
    // Maximum tokens per request
    MAX_TOKENS: 2000,
    
    // Timeout in milliseconds
    TIMEOUT: 30000
  },

  // Gift Recommendation Settings
  RECOMMENDATIONS: {
    // Number of gift suggestions to generate
    COUNT: 5,
    
    // Maximum price for recommendations (in dollars)
    MAX_BUDGET: 2000,
    
    // Minimum price for recommendations (in dollars)
    MIN_BUDGET: 10,
    
    // Default budget (in dollars)
    DEFAULT_BUDGET: 500
  },

  // Product Search Settings
  PRODUCT_SEARCH: {
    // Enable/disable product enrichment (searching for real products)
    ENABLED: true,
    
    // Stores to prioritize for different categories
    STORE_MAPPING: {
      'electronics': ['Amazon', 'Best Buy', 'Newegg'],
      'fashion': ['Amazon', 'H&M', 'Zara', 'ASOS'],
      'home': ['Amazon', 'Wayfair', 'Target', 'IKEA'],
      'sports': ['Amazon', 'Dick\'s Sporting Goods', 'REI'],
      'books': ['Amazon', 'Barnes & Noble', 'Book Depository'],
      'gaming': ['Amazon', 'GameStop', 'Best Buy'],
      'art': ['Amazon', 'Etsy', 'Blick Art Materials'],
      'music': ['Amazon', 'Sweetwater', 'Guitar Center'],
      'cooking': ['Amazon', 'Williams Sonoma', 'Sur La Table'],
      'fitness': ['Amazon', 'Dick\'s Sporting Goods', 'Rogue Fitness'],
      'default': ['Amazon', 'Etsy', 'eBay']
    }
  },

  // UI Settings
  UI: {
    // Animation duration in milliseconds
    ANIMATION_DURATION: 300,
    
    // Show loading spinner
    SHOW_LOADING: true,
    
    // Enable dark mode (true/false)
    DARK_MODE: true,
    
    // Chart configuration
    CHART: {
      TYPE: 'scatter',
      RESPONSIVE: true,
      MAINTAIN_ASPECT_RATIO: true,
      HEIGHT: 500
    }
  },

  // Personality Types
  PERSONALITIES: [
    { value: 'minimalist', label: 'Minimalist (appreciates simplicity)' },
    { value: 'adventurous', label: 'Adventurous (loves new experiences)' },
    { value: 'practical', label: 'Practical (values functionality)' },
    { value: 'artistic', label: 'Artistic (creative & aesthetic)' },
    { value: 'social', label: 'Social (enjoys sharing with others)' },
    { value: 'tech-savvy', label: 'Tech-Savvy (loves gadgets)' },
    { value: 'homebody', label: 'Homebody (prefers comfort at home)' }
  ],

  // Occasions
  OCCASIONS: [
    { value: 'birthday', label: 'Birthday' },
    { value: 'holiday', label: 'Holiday' },
    { value: 'graduation', label: 'Graduation' },
    { value: 'anniversary', label: 'Anniversary' },
    { value: 'wedding', label: 'Wedding' },
    { value: 'congratulations', label: 'Congratulations' },
    { value: 'just-because', label: 'Just Because' }
  ],

  // Happiness Score Thresholds (visual feedback)
  HAPPINESS_THRESHOLDS: {
    LOW: 5,      // Score < 5 = low match
    MEDIUM: 7,   // Score 5-7 = medium match
    HIGH: 10     // Score > 7 = high match
  }
};

// Export for use in modules
if (typeof module !== 'undefined' && module.exports) {
  module.exports = CONFIG;
}