# 📊 TradingView Chart Analyzer with Chrome Extension

🚀 **AI-Powered Technical Analysis for TradingView Charts**

An intelligent n8n workflow that analyzes TradingView stock and cryptocurrency charts using OpenAI's GPT-4o-mini. Perfect for novice traders who want AI-powered insights delivered through a Chrome extension.

## 🎯 Project Name & Description

**Project Name:**
```
tradingview-chart-analyzer
```

**Description:**
```
AI-powered technical analysis tool for TradingView charts. 
A Chrome extension paired with n8n backend that analyzes 
stock and crypto charts using OpenAI's vision capabilities. 
Provides beginner-friendly trading insights with risk disclaimers.
```

## ✨ Features

- **Chart Analysis**: Analyzes TradingView chart images via webhook
- **AI-Powered Insights**: Uses GPT-4o-mini for technical analysis
- **Beginner-Friendly**: Explains market direction in simple language
- **Risk Disclaimer**: Includes legal warnings about trading advice
- **Chrome Extension Integration**: Seamless integration with browser
- **Fast Response**: Real-time analysis delivery
- **Webhook-Based**: Easy integration with any front-end

## 🔄 How It Works

```
1. User captures TradingView chart screenshot
2. Chrome extension sends image to n8n webhook
3. OpenAI analyzes the chart image
4. AI returns technical analysis
5. Results displayed in extension popup
```

## 🛠️ Technical Stack

| Component | Technology |
|-----------|-----------|
| **Workflow Platform** | n8n |
| **AI Model** | OpenAI GPT-4o-mini |
| **Integration** | Webhook (HTTP POST) |
| **Frontend** | Chrome Extension |
| **Input** | Base64 encoded images |
| **Output** | Text analysis |

## 📋 Workflow Components

### 1. **Webhook Node**
- Receives POST requests from Chrome extension
- Accepts base64 encoded chart images
- Triggers workflow immediately

### 2. **OpenAI Node**
- Analyzes chart images using GPT-4o-mini
- Uses vision capabilities for chart interpretation
- Provides technical analysis of:
  - Support & Resistance levels
  - Trend direction
  - Key indicators
  - Entry/Exit signals

### 3. **Response Node**
- Returns analysis to Chrome extension
- Formats response as readable text
- Delivers results instantly

## 🚀 Quick Start

### Prerequisites
- n8n instance (self-hosted or cloud)
- OpenAI API key
- Chrome browser
- Basic understanding of technical analysis

### Setup Steps

1. **Import Workflow**
   - Go to n8n
   - Create new workflow
   - Import JSON file
   - Deploy

2. **Configure OpenAI**
   - Add your OpenAI API key
   - Select GPT-4o-mini model
   - Save credentials

3. **Build Chrome Extension**
   - Create simple HTML popup
   - Add JavaScript to capture screenshots
   - Send images to webhook URL
   - Display results

4. **Test**
   - Take TradingView chart screenshot
   - Send via extension
   - Verify analysis response

## 💻 Chrome Extension Example

Basic extension structure:

```javascript
// content.js - Capture and send screenshot
function analyzeChart() {
  const imageData = captureChartScreenshot();
  
  fetch('YOUR_WEBHOOK_URL', {
    method: 'POST',
    headers: {'Content-Type': 'application/json'},
    body: JSON.stringify({
      chart_image: imageData,
      symbol: getCurrentSymbol()
    })
  })
  .then(r => r.text())
  .then(analysis => displayResults(analysis));
}
```

## 📊 AI Prompt Details

The workflow uses a specialized prompt for financial analysis:

```
"You are an expert financial analyst tasked with providing 
advanced technical analyses of stock or cryptocurrency charts. 
Your analysis is based on technical indicators and provides 
simple insights for novice traders. Explain where you expect 
the market is moving. Warn traders this is NOT binding advice. 
Explain everything in simple language."
```

## 🎓 What the AI Analyzes

- **Trend Direction**: Up, down, or sideways
- **Support/Resistance**: Key price levels
- **Indicators**: Moving averages, RSI, MACD, etc.
- **Entry Points**: Potential buying opportunities
- **Exit Signals**: When to consider selling
- **Risk Assessment**: Potential downside risks

## 💰 Costs

**Per Analysis:**
- OpenAI GPT-4o-mini: ~$0.001-0.003 per image

**Monthly Estimates:**
- 100 analyses/day: ~$3-9/month
- 1000 analyses/day: ~$30-90/month

## ⚠️ Important Disclaimers

1. **NOT Investment Advice**: Analysis is educational only
2. **Market Risk**: Trading always involves risk
3. **No Guarantees**: Past performance ≠ future results
4. **Do Your Research**: Always verify before trading
5. **Seek Professional Advice**: Consult a financial advisor

## 📁 Files Included

- `workflow.json` - Complete n8n workflow
- `README.md` - This documentation
- `SETUP.md` - Detailed setup instructions
- `CHROME_EXTENSION_GUIDE.md` - Extension development guide
- `LICENSE` - MIT License

## 🔐 Security Considerations

- ✅ Never share your OpenAI API key
- ✅ Use environment variables for secrets
- ✅ Validate webhook requests
- ✅ Implement rate limiting
- ✅ Use HTTPS for webhook

## 🚀 Deployment

### n8n Cloud
1. Import workflow
2. Add OpenAI credentials
3. Activate
4. Get webhook URL

### Self-Hosted n8n
1. Ensure publicly accessible
2. Import workflow
3. Configure OpenAI API
4. Activate
5. Use public webhook URL

## 📱 Chrome Extension Distribution

**Option 1: Personal Use**
- Load unpacked extension
- Enable Developer Mode
- Use on your machine

**Option 2: Chrome Web Store**
- Package extension
- Create developer account
- Submit for review
- Publish to store

## 🔄 Workflow Architecture

```
┌─────────────────────────────┐
│  Chrome Extension           │
│  (Captures screenshot)      │
└────────────┬────────────────┘
             │ POST with image
             │
┌────────────▼────────────────┐
│  n8n Webhook                │
│  (Receives image data)      │
└────────────┬────────────────┘
             │
┌────────────▼────────────────┐
│  OpenAI GPT-4o-mini         │
│  (Analyzes chart image)     │
└────────────┬────────────────┘
             │ Analysis text
┌────────────▼────────────────┐
│  Response Node              │
│  (Returns to extension)     │
└────────────┬────────────────┘
             │ HTTP Response
             │
┌────────────▼────────────────┐
│  Extension Popup            │
│  (Displays analysis)        │
└─────────────────────────────┘
```

## 🎨 Customization Options

### Modify AI Behavior
- Edit the prompt text
- Adjust analysis style
- Add specific indicators to analyze
- Change response format

### Extend Functionality
- Add symbol lookup
- Store analysis history
- Compare multiple timeframes
- Add trading alerts
- Export analysis reports

## 📚 Related Resources

- **TradingView API**: https://www.tradingview.com/api/
- **OpenAI Vision**: https://platform.openai.com/docs/vision
- **Chrome Extension Dev**: https://developer.chrome.com/docs/extensions/
- **n8n Docs**: https://docs.n8n.io
- **GPT-4o-mini**: https://platform.openai.com/docs/models

## 🐛 Troubleshooting

**Issue: Webhook not receiving images**
- Verify URL is correct
- Check CORS settings
- Ensure n8n is publicly accessible

**Issue: Slow analysis**
- Check OpenAI API quota
- Verify internet connection
- Consider image size

**Issue: Chrome extension errors**
- Check permissions
- Verify API endpoint
- Review browser console

## 📝 Example Analysis Output

```
Technical Analysis for AAPL 1H Chart:

📊 Current Trend: BULLISH
The chart shows a strong uptrend with prices above the 200-MA.

🎯 Key Levels:
- Resistance: $189.50
- Support: $185.20

📈 Indicators:
- RSI: 65 (Slightly overbought)
- MACD: Bullish crossover
- MA(50): Above MA(200) ✓

💡 Insight:
Market appears strong with bullish momentum. 
Watch for pullback to $187 for entry.

⚠️ DISCLAIMER: This is not financial advice. 
Trade at your own risk.
```

## 🤝 Contributing

Improvements welcome! Consider:
- Better prompt engineering
- Additional indicators
- Historical tracking
- Backtesting features
- Multi-timeframe analysis

## 📄 License

MIT License - Free to use and modify

## 🎯 Project Goals

- ✅ Analyze TradingView charts via AI
- ✅ Provide beginner-friendly insights
- ✅ Chrome extension integration
- ✅ Fast response times
- ✅ Risk disclaimers
- 🎯 Expand to more markets
- 🎯 Add alert functionality
- 🎯 Implement backtesting

## 📞 Support

- **Issues**: Report on GitHub
- **Questions**: Check documentation
- **API Help**: OpenAI support
- **n8n Help**: n8n community

---

**Made for traders who want AI-powered analysis** 📈

**Disclaimer**: This tool is educational only. Always conduct your own research and consult with financial advisors before trading.
