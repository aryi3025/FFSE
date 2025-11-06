FFSE - Fantasy Football Stock Exchange 📈🏈
A comprehensive fantasy football analytics platform that helps you identify breakout players, analyze trends, and make data-driven roster decisions. Built as a single-page web application with advanced visualizations and real-time rankings.
🌟 Features
Player Rankings

WR Rankings: 8-tier system from Elite WR1 to Depth players
RB Rankings: 7-tier system from Elite RB1 to Depth Chart players
TE Rankings: 6-tier system from Elite TE to Depth players
Rank-based top tiers ensure elite players stand out
Sample size protection prevents one-game wonders from ranking too high
Inactive player tracking with automatic tier adjustments

Dashboard Leaderboards
11 rotating leaderboard categories tracking last 3 weeks performance:

Volume Monsters (RB): Highest opportunities per game
Efficiency Elites: Best fantasy points per touch
Red Zone Kings (WR): Most red zone targets
Red Zone Backs (RB): Most red zone opportunities
RB Efficiency: Highest yards per carry
High-Volume Alphas (WR): Most targets per game
Air Yards Leaders (WR): Highest air yards per game
Pass-Catching Backs (RB): Highest target share
Target Leaders (TE): Most targets per game
Red Zone Dominance (TE): Best red zone production (RZ Score = RZ Targets + RZ TDs × 3)
Total TD Leaders (WR): Most total touchdowns (receiving + rushing)

Advanced Analytics

Custom Scatterplots: Compare any two stats across 15+ metrics
Position-Specific Stats: Tailored metrics for WR, RB, and TE
Available Metrics Include:

Scoring: Fantasy Points/Game, Total TDs, Receiving TDs, Rushing TDs, Red Zone TDs
Volume: Targets, Receptions, Opportunities, Carries, Red Zone Targets
Efficiency: Yards per Touch, TD Rate, Catch Rate, YAC per Reception
Advanced: Air Yards, Target Share %, Team Points per Game


Player Highlighting: Highlight up to 4 players simultaneously
Week Range Filters: All weeks, last 3/5 weeks, or custom ranges
Quick Presets: One-click access to popular stat combinations

Team Outlook

Team Analysis Charts:

Pie charts showing target/opportunity distribution among top 5 players
Bar charts displaying total volume by player
League comparison charts showing team vs. rest of league
Season-long trend visualization (stacked bar for WR, line chart for RB)


Division Grid: All 8 NFL divisions with team cards
Time Frame Selection: Single week, last 3/5 weeks, or full season
Position Toggle: Switch between WR and RB analysis

Player Cards & Modals

Performance Consistency Charts: Week-by-week scoring trends
Player Profile Analysis: Volume vs. efficiency metrics
Community Sentiment: Buy/Hold/Sell voting with live percentages
Comprehensive Stats:

Average points per game
Targets/Opportunities per game
Comparison vs. position average (Top 24 for WR/RB, Top 12 for TE)
Tags: Buy Low, Sell High, RZ Trend Up, Momentum badges



Scoring Format Support

PPR (Points Per Reception)
Half-PPR (0.5 points per reception)
Standard (No reception points)
Live switching between formats with instant recalculation

Smart Data Processing

Automatic tier demotion for inactive players (2+ weeks without playing)
Sample size protection (players with <2 games capped at lower tiers)
Position-specific tier logic
Special player exceptions (injury tracking, return protocols)
Momentum calculation across rolling 6-week windows

🎨 Design

Dark Theme: Professional dark UI optimized for extended viewing
Team Colors: Official NFL team colors throughout all visualizations
Responsive Charts: Interactive Chart.js visualizations
Smooth Animations: Carousel scrolling, chart transitions, and page navigation
Matte Cards: Elevated card design with subtle shadows and borders

📊 Data Format
Required CSV Files
Upload three CSV files through the Admin Panel:
WR Data (Wide Receivers)
Required columns:

Player, Team, Week, FPTS (or Fpts)
TGT, REC, REC_YDS, REC_TD
AIR, CATCHABLE, YAC
RZ TGT (or RZ_TGT), RZ_REC_TD
% TM (target share percentage)
Exp_Ft_Points (or Exp_Ft_Points_PPR)
FPTS_Variance (or FPTS_Variance_PPR)
Optional: RUSH_YDS, RUSH_TD, RZ_RUSH_TD, CARRIES

RB Data (Running Backs)
Required columns:

Player, Team, Week, FPTS (or Fpts)
ATT, YDS (rushing yards), RUSH_TD
TGT, REC, REC_YDS, REC_TD
RB Opp (total opportunities)
RZ_RUSH_ATT, RZ TGT (or RZ_TGT)
RZ_REC_TD, RZ_RUSH_TD
YBCON, YACON
Exp_Ft_Points, FPTS_Variance

TE Data (Tight Ends)
Required columns:

Player, Team, Week, FPTS (or Fpts)
TGT, REC, YDS (or REC_YDS), REC_TD
AIR, CATCHABLE, YAC
RZ TGT (or RZ_TGT), RZ_REC_TD
% TM (target share percentage)
Exp_Ft_Points, FPTS_Variance
Optional: RZ_RUSH_TD

Scoring Format Columns
For PPR/Half-PPR/Standard support, include:

Exp_Ft_Points_PPR, Exp_Ft_Points_HALF, Exp_Ft_Points_STD
FPTS_Variance_PPR, FPTS_Variance_HALF, FPTS_Variance_STD

🚀 Deployment
Option 1: Static Hosting (Vercel, Netlify, etc.)

Prepare the file:

Rename fantasy-stock-exchange-v44-5.html to index.html
Place in root directory of your repository


Deploy to Vercel:

bash   # Install Vercel CLI (optional)
   npm i -g vercel
   
   # Deploy
   vercel
Or use Vercel's GitHub integration for automatic deployments

Settings:

Framework Preset: Other
Build Command: Leave empty
Output Directory: . (root)
Install Command: Leave empty



Option 2: GitHub Pages

Push to GitHub repository
Go to Settings → Pages
Select branch and root folder
GitHub will serve index.html automatically

Option 3: Local Development
Simply open the HTML file in a modern web browser:
bash# Option 1: Direct open
open index.html

# Option 2: Local server (recommended for testing)
python -m http.server 8000
# Then visit http://localhost:8000
🔧 Admin Panel
Access the admin panel to upload and manage data:

Access Admin Mode:

The Admin tab appears automatically (no password required in current version)
Located in the top navigation bar


Upload Data:

Upload WR, RB, and TE CSV files
Data is processed automatically
All pages update with new data instantly
"Last updated" timestamp shows current data age


Data Storage:

Data stored in browser's localStorage
Persists between sessions
Clear browser data to reset



🛠️ Technology Stack

Frontend: Vanilla JavaScript (ES6+)
Charts: Chart.js 3.9.1
CSV Parsing: PapaParse 5.3.0
Styling: Pure CSS with CSS Variables
Data Storage: Browser localStorage
Responsive Design: CSS Grid and Flexbox

📱 Browser Support

Chrome/Edge 90+
Firefox 88+
Safari 14+
Mobile browsers (iOS Safari, Chrome Mobile)

🎯 Use Cases

Weekly Lineup Decisions: Identify trending players and fading stars
Trade Analysis: Evaluate player value with efficiency and volume metrics
Waiver Wire: Spot breakout candidates with momentum indicators
Buy Low/Sell High: Find undervalued players in good situations
DFS Research: Quick access to volume and efficiency leaders
Dynasty Valuation: Long-term trend analysis with full season data

📈 Data Analysis Features
Momentum Calculation

6-week rolling window (last 3 weeks vs. prior 3 weeks)
Position-specific weighting:

WR: 50% targets, 30% receptions, 20% fantasy points
RB: 50% opportunities, 30% carries, 20% fantasy points
TE: Same as WR (target-based)



Tier Assignment Logic

Top Tiers: Rank-based (Elite: top 4, High-End: ranks 5-8)
Mid Tiers: Point-based thresholds
Sample Size Rules:

1 game: capped at WR3/RB3/TE4 tier
2 games: eligible for WR2/RB2/TE3 tier
3+ games: full eligibility


Inactive Penalties: -3.5 PPG for 2+ weeks without playing

Red Zone Scoring

RZ Score (TE): RZ Targets + (RZ TDs × 3)
TDs weighted 3x because they're more valuable than targets
Calculated per game over last 3 weeks

🔒 Privacy & Data

No backend server: All processing happens in your browser
No data collection: No analytics, tracking, or data sent to external servers
Local storage only: Data persists in browser localStorage
No authentication required: Open access (admin panel accessible to all)

📝 Version History
v44.5 (Latest)

Changed default landing page to WR Rankings
Fixed TE receiving yards calculation (YDS column fallback)
Fixed Target Leaders (TE) leaderboard data calculation
Added all 3 new leaderboards to carousel
Fixed RZ TD calculation (RZ_REC_TD + RZ_RUSH_TD)

v44.0

Added 9 new stats to Advanced Analytics (TDs, efficiency metrics)
Added 3 new leaderboards (Target Leaders TE, RZ Dominance TE, Total TD Leaders WR)
Enhanced TD data aggregation across all positions
Added WR rushing stats tracking

v43.0

Fixed Tucker Kraft inactive status
Improved player injury tracking

v42.0

Complete TE Rankings page with 6-tier system
TE Advanced Analytics support
TE Top Movers widgets

🤝 Contributing
This is a single-file application, making contributions straightforward:

The entire app is in one HTML file (~19,000 lines)
All JavaScript, CSS, and HTML are contained within
No build process or dependencies to install
Make edits directly to the HTML file
