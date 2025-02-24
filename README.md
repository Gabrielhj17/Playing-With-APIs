# Playing With APIs

A collection of examples, experiments, and mini-projects demonstrating how to interact with various public and private APIs.

![API Illustration](https://via.placeholder.com/800x400?text=API+Playground)

## 🌐 Overview

This repository serves as both a learning resource and reference implementation for working with different types of APIs. From RESTful services to GraphQL endpoints, webhook integrations to OAuth flows, this collection demonstrates best practices and common patterns for API consumption and integration.

## 📋 Contents

The repository is organized by API type or service:

- **REST APIs**
  - Weather data retrieval
  - Social media integrations
  - E-commerce product information
  
- **GraphQL Examples**
  - Basic queries and mutations
  - Subscription implementations
  - Schema exploration
  
- **Authentication Demos**
  - API Key authentication
  - OAuth 2.0 flows
  - JWT token handling
  
- **Real-time APIs**
  - WebSocket implementations
  - Server-Sent Events
  - Polling strategies

## 🚀 Getting Started

### Prerequisites

- Python 3.7+ or Node.js 14+
- API keys for respective services (see documentation in each folder)
- Basic understanding of HTTP and API concepts

### Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/Gabrielhj17/Playing-With-APIs.git
   cd Playing-With-APIs
   ```

2. Install dependencies for your preferred language:
   
   **For Python projects:**
   ```bash
   pip install -r requirements.txt
   ```
   
   **For JavaScript projects:**
   ```bash
   npm install
   ```

3. Configure API credentials:
   - Copy `.env.example` to `.env`
   - Add your API keys to the `.env` file

## 🔍 Examples

### Weather API Example

```python
import requests
from dotenv import load_dotenv
import os

load_dotenv()

def get_weather(city):
    """Get current weather for a given city"""
    api_key = os.getenv("WEATHER_API_KEY")
    url = f"https://api.weatherapi.com/v1/current.json?key={api_key}&q={city}"
    
    response = requests.get(url)
    if response.status_code == 200:
        return response.json()
    else:
        return {"error": f"Failed to retrieve data: {response.status_code}"}

# Example usage
if __name__ == "__main__":
    city = "London"
    weather_data = get_weather(city)
    print(f"Current temperature in {city}: {weather_data['current']['temp_c']}°C")
```

### GitHub API Example (with Authentication)

```javascript
const axios = require('axios');
require('dotenv').config();

async function getRepoInfo(owner, repo) {
  try {
    const response = await axios.get(`https://api.github.com/repos/${owner}/${repo}`, {
      headers: {
        'Authorization': `token ${process.env.GITHUB_TOKEN}`
      }
    });
    
    return {
      name: response.data.name,
      description: response.data.description,
      stars: response.data.stargazers_count,
      forks: response.data.forks_count,
      issues: response.data.open_issues_count
    };
  } catch (error) {
    console.error('Error fetching repo info:', error.message);
    return null;
  }
}

// Example usage
getRepoInfo('Gabrielhj17', 'Playing-With-APIs')
  .then(info => console.log(info))
  .catch(err => console.error(err));
```

## 📊 API Categories Explored

This repository includes examples for APIs in the following categories:

- **Public Data APIs** - Weather, news, public records
- **Social Media APIs** - Twitter, Facebook, Instagram
- **E-commerce APIs** - Product catalogs, inventory, pricing
- **Financial APIs** - Stock data, cryptocurrency, banking
- **Map/Location APIs** - Geocoding, directions, points of interest
- **Communication APIs** - SMS, email, push notifications
- **AI/ML APIs** - Natural language processing, image recognition
- **Entertainment APIs** - Movies, music, games

## 🔧 Tools & Libraries

The examples in this repository use various libraries and tools such as:

- **Python**: Requests, aiohttp, httpx
- **JavaScript**: Axios, node-fetch, Apollo Client
- **API Tools**: Postman collections, Insomnia workspaces
- **Authentication**: OAuth libraries, JWT helpers

## 📝 API Best Practices

Throughout this repository, you'll find implementations of API best practices:

- Rate limiting and throttling
- Proper error handling
- Response caching
- Pagination handling
- Security considerations

## 🛠️ Building Your Own API Client

The `/client-builder` directory contains a framework for constructing your own API client libraries, with examples for:

- Class-based client design
- Method organization
- Error standardization
- Documentation generation

## 📚 Learning Resources

- [RESTful API Design](https://restfulapi.net/)
- [GraphQL Documentation](https://graphql.org/learn/)
- [OAuth 2.0 Simplified](https://www.oauth.com/)
- [API Security Best Practices](https://owasp.org/www-project-api-security/)

## 🤝 Contributing

Contributions are welcome! If you'd like to add examples for new APIs or improve existing ones:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-api-example`)
3. Commit your changes (`git commit -am 'Add example for New API'`)
4. Push to the branch (`git push origin feature/new-api-example`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Thanks to all the API providers with great documentation
- The open-source community for creating amazing API libraries
- All contributors who have helped improve this repository

---

**Note**: Remember to never commit your API keys to version control. Always use environment variables or secure secret management.

## ✉️ Contact

Gabriel H-J - [@Gabrielhj17](https://github.com/Gabrielhj17)

Project Link: [https://github.com/Gabrielhj17/Playing-With-APIs](https://github.com/Gabrielhj17/Playing-With-APIs)
