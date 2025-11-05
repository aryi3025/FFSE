# FFSE
Fantasy football stock exchange: A fantasy football dashboard for tracking player performance, trends, and team analytics.
# FFSE - Fantasy Football Stock Exchange

A sophisticated fantasy football analytics platform that transforms player performance data into actionable insights using stock market-inspired metrics and visualizations.

## 🎯 Overview

FFSE (Fantasy Football Stock Exchange) is a single-page web application that provides comprehensive analytics for fantasy football wide receivers (WR) and running backs (RB). The platform features interactive dashboards, advanced analytics, team outlooks, and community sentiment tracking.

## ✨ Key Features

### 📊 Dashboard & Analytics
- **Top Movers Dashboard**: Real-time player performance tracking with customizable metrics carousel
- **8 Specialized Leaderboards**:
  - Volume Monsters (RB) & High-Volume Alphas (WR)
  - Red Zone Kings (WR) & Red Zone Backs (RB)
  - Efficiency Elites & RB Efficiency
  - Air Yards Leaders (WR) & Pass-Catching Backs (RB)
- **Advanced Analytics**: Interactive scatter plots for position-specific analysis with multi-player comparison
- **Team Outlook**: Comprehensive team analysis with target/opportunity share breakdowns

### 📈 Player Analysis
- **Detailed Player Modals** with:
  - Performance consistency charts
  - Player profile visualizations
  - Position-specific statistics (targets, receptions, yards, TDs)
  - Community sentiment tracking (Buy/Hold/Sell voting)
  - Comprehensive tooltips for all metrics

### 🏈 Team Analysis Tools
- **32 NFL Teams Coverage** with official team branding
- **Position Group Analysis** (WR/RB)
- **Time Frame Selection**: Single week, Last 3/5 weeks, Season-long
- **Multiple Chart Types**:
  - Pie charts (share distribution)
  - Bar charts (volume analysis)
  - League comparison overlays
  - Season-long trend analysis

### 🎨 UI/UX Features
- Dark theme optimized for extended viewing
- Responsive design for all screen sizes
- Smooth animations and transitions
- Matte card design with team color integration
- Collapsible division grids (AFC/NFC)
- Real-time data filtering and sorting

### 🔐 Admin Panel
- Secure admin authentication
- CSV data upload for WR and RB statistics
- Data validation and processing
- Upload status tracking
- Last updated timestamp display

## 🛠️ Technology Stack

### Frontend
- **Pure HTML/CSS/JavaScript** - No framework dependencies
- **Chart.js** - Interactive data visualizations
- **PapaParse** - CSV parsing for data uploads
- **CSS Custom Properties** - Dynamic theming system

### Data Storage
- **LocalStorage** - Client-side data persistence
- **Google Sheets API** - Waitlist management (optional)

### External Dependencies
```html
<!-- Chart.js for visualizations -->
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<script src="https://cdn.jsdelivr.net/npm/chartjs-plugin-annotation"></script>

<!-- CSV parsing -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/PapaParse/5.4.1/papaparse.min.js"></script>
```

## 📁 Project Structure

```
fantasy-stock-exchange-v34.html
├── HTML Structure
│   ├── Navigation
│   ├── Dashboard (Top Movers)
│   ├── WR Leaderboards
│   ├── RB Leaderboards
│   ├── All Leaderboards
│   ├── Advanced Analytics
│   ├── Team Outlook
│   ├── Admin Panel
│   └── Footer (Waitlist)
├── CSS Styles
│   ├── Base & Reset
│   ├── Layout & Navigation
│   ├── Dashboard Components
│   ├── Leaderboard Styles
│   ├── Modal Styles
│   ├── Chart Containers
│   ├── Team Cards
│   └── Admin Panel
└── JavaScript
    ├── Data Management
    ├── Chart Rendering
    ├── Modal Management
    ├── Navigation
    ├── Admin Functions
    └── Utility Functions
```

## 🚀 Getting Started

### Prerequisites
- Modern web browser (Chrome, Firefox, Safari, Edge)
- Local web server (for development)
- CSV data files for WR and RB statistics

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/fantasy-stock-exchange.git
cd fantasy-stock-exchange
```

2. **Open the application**
```bash
# Option 1: Simple HTTP server (Python)
python -m http.server 8000

# Option 2: Simple HTTP server (Node.js)
npx http-server

# Option 3: Just open the HTML file in a browser
# Note: Some features may require a web server
```

3. **Access the application**
```
http://localhost:8000/fantasy-stock-exchange-v34.html
```

### First-Time Setup

1. Navigate to the Admin Panel (footer link)
2. Login with admin credentials (default: see Admin section)
3. Upload WR and RB CSV data files
4. Data will be processed and stored in browser LocalStorage
5. Navigate back to Dashboard to view analytics

## 📊 Data Format

### Required CSV Columns

#### WR Data
```csv
Player,Team,Week,Targets,Receptions,Yards,TDs,Target_Share,Air_Yards,Redzone_Targets,Points_Per_Target
```

#### RB Data
```csv
Player,Team,Week,Opportunities,Carries,Targets,Yards,TDs,Opportunity_Share,Redzone_Opportunities,Points_Per_Opportunity,Yards_Per_Attempt
```

### Data Processing
- Automatic aggregation for season totals
- Change calculation (current week vs. prior 3 weeks average)
- Ranking across multiple metrics
- Community sentiment integration

## 🔧 Configuration

### Admin Access
Default admin password can be set in the code:
```javascript
// Line ~16260
if (password === 'your-admin-password') {
    // Admin authenticated
}
```

### Google Sheets Integration (Optional)
For waitlist functionality:

1. Create a Google Sheet
2. Go to Extensions > Apps Script
3. Add the provided doPost function (see HTML comments)
4. Deploy as web app
5. Update the script URL in the code (line ~13630)

### Team Colors
Team color palettes are defined in the `TEAM_COLORS` object:
```javascript
const TEAM_COLORS = {
    'ARI': { primary: '#97233f', secondary: '#ffb612' },
    // ... all 32 teams
};
```

## 🎨 Customization

### Color Scheme
Modify CSS custom properties in `:root`:
```css
:root {
    --bg-primary: #000;
    --bg-secondary: #0a0a0a;
    --text-primary: #fff;
    --positive: #30d158;
    --negative: #ff453a;
}
```

### Leaderboard Metrics
Add or modify leaderboards by updating the carousel configuration:
```javascript
// Line ~14900
const dashboardLeaderboards = [
    { title: 'Volume Monsters', position: 'RB', ... },
    // Add custom leaderboards
];
```

### Chart Configurations
Chart.js options are configurable throughout the codebase:
```javascript
const chartOptions = {
    responsive: true,
    maintainAspectRatio: false,
    // Customize appearance
};
```

## 🧪 Development

### Key Functions

#### Data Management
- `processAllData()` - Aggregates and processes uploaded data
- `calculateChange()` - Computes week-over-week changes
- `getTopPlayers()` - Filters and ranks players by metric

#### Rendering
- `renderLeaderboard()` - Creates leaderboard cards
- `openPlayerModal()` - Displays detailed player analytics
- `renderConsistencyChart()` - Performance visualization
- `renderPlayerProfileChart()` - Position-specific metrics

#### Navigation
- `navigateToPage()` - Single-page app routing
- `showAllLeaderboards()` - Consolidated leaderboard view

#### Team Analysis
- `renderTeamAnalysis()` - Team-specific insights
- `renderPieChart()` - Share distribution
- `renderBarChart()` - Volume metrics
- `renderSeasonLong()` - Trend analysis

### Debug Mode
Enable console logging for development:
```javascript
const DEBUG = true; // Set at top of script section
```

## 📈 Version History

### v34 - Current (Streamlined Player Modals)
- Removed AI Analysis section
- Removed redundant chart tabs
- New horizontal community sentiment bar
- Improved modal layout and focus

### v33 - Enhanced Tooltips
- Comprehensive modal stat tooltips
- Position-specific explanations
- Dashboard metric tooltips

### v31 - Visual Improvements
- Fixed bar alignment issues
- Two-column team label layout
- Simplified color system
- Redesigned sentiment card

### v30 - Team Analysis
- Comprehensive team analysis section
- Multiple chart types
- League comparison toggle
- Collapsible divisions

See HTML header for complete version history.

## 🤝 Contributing

### Code Style
- Use consistent indentation (4 spaces)
- Comment complex logic sections
- Follow existing naming conventions
- Test across multiple browsers

### Submitting Changes
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Development Workflow
1. Test changes locally
2. Verify data processing
3. Check responsive design
4. Validate chart rendering
5. Test admin panel functionality

## 🐛 Known Issues

- LocalStorage has size limitations (~5-10MB depending on browser)
- CSV must be properly formatted (use provided templates)
- Admin panel requires page refresh after logout
- Some features require HTTPS in production

## 🔮 Future Enhancements

- [ ] User authentication system
- [ ] Real-time data updates via API
- [ ] Export functionality for reports
- [ ] Mobile app version
- [ ] Social sharing features
- [ ] Advanced filtering options
- [ ] Custom leaderboard creation
- [ ] Historical data comparison
- [ ] Predictive analytics
- [ ] League integration

## 📝 License

This project is currently unlicensed. Please contact the repository owner for usage permissions.

## 📧 Contact

For questions, suggestions, or issues:
- Open an issue on GitHub
- Submit via the waitlist form in the app footer

## 🙏 Acknowledgments

- Chart.js for visualization capabilities
- PapaParse for CSV processing
- NFL teams for official branding
- Fantasy football community for inspiration

---

**Current Version:** v34  
**Last Updated:** See in-app footer for data timestamp  
**Status:** Active Development
