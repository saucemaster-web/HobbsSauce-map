# Hobbs Sauce Interactive Map

An interactive map showcasing Hobbs Sauce locations across Philadelphia, featuring product tracking, mobile optimization, and Squarespace integration.

## 🗺️ Live Demo

**Main Site**: [https://saucemaster-web.github.io/HobbsSauce-map/](https://saucemaster-web.github.io/HobbsSauce-map/)

## 📱 Features

### Interactive Map
- **Leaflet.js** powered map with custom markers
- **Mobile-optimized** touch interactions (tap to show info, tap again to navigate)
- **Responsive design** with proper zoom controls and bounds
- **Custom marker icons** (black for retail, orange for restaurants)

### Product Tracking System
- **Hobbs Shake – Retail**: Locations selling shake products
- **Hobbs Sauce – Retail**: Locations selling sauce products  
- **Restaurant Partner**: Dining establishments featuring Hobbs products

### Smart Filtering
- **All Locations**: Shows complete directory
- **Retail Only**: Filter for product purchase locations
- **Restaurants**: Filter for dining establishments
- **Real-time filtering** with no page reload

### Location Cards
- **Uniform card layout** with consistent heights
- **Product badges** showing available offerings
- **Direct actions**: Website links and "Show on Map" buttons
- **Business information**: Address, phone, neighborhood details

## 🏗️ Technical Architecture

### Frontend Stack
- **Vanilla JavaScript** - No framework dependencies
- **Leaflet.js v1.9.4** - Interactive mapping
- **CSS Grid & Flexbox** - Responsive layouts
- **Progressive Enhancement** - Works without JavaScript

### Data Management
- **Embedded data** in `index.html` (`const hobbsLocations = [...]`) to avoid cross-origin CSV fetches.
- Original source: `data/hobbs_locations.csv` (for reference and updates).
- **GitHub Pages** hosting with automatic updates.
- **Version control** through Git for all changes.
- **Structured data** with validation and consistency.

### Mobile Optimization
- **Touch-first design** with hover fallbacks
- **Responsive breakpoints** for all screen sizes
- **Performance optimized** with efficient rendering
- **Accessibility compliant** with ARIA labels and keyboard navigation

## 📂 Project Structure

```
HobbsSauceMapv2/
├── index.html                      # Main standalone version
├── index-squarespace-clean.html    # Squarespace-optimized version
├── data/
│   └── hobbs_locations.csv        # Location data source
├── assets/
│   ├── hobbs-black.png            # Retail location marker
│   ├── hobbs-orange.png           # Restaurant marker
│   └── [location-logos]/          # Business logo assets
└── README.md                      # Project documentation
```

## 🔧 Setup & Development

### Prerequisites
- Git for version control
- Text editor (VS Code recommended)
- Modern web browser for testing
- Optional: Local web server for development

### Local Development
1. **Clone the repository**
   ```pwsh
   git clone https://github.com/saucemaster-web/HobbsSauce-map.git
   cd HobbsSauce-map
   ```

2. **Open in browser**
   - Direct file access: open `index.html`
   - Local server (recommended):
     ```pwsh
     python -m http.server 8080
     ```

3. **Make changes**
   - Add or edit locations directly in `index.html` inside `hobbsLocations`.
   - Keep `lastUpdated` current for each entry.
   - Optionally mirror changes in `data/hobbs_locations.csv` for history.
   - Modify styling in the `<style>` section as needed.

### Deployment
```bash
git add .
git commit -m "Description of changes"
git push origin main
```
Changes go live automatically via GitHub Pages (1-5 minute delay).

## 📊 Data Format

### CSV Structure (reference)
```csv
name,type,address,googleMapsLink,website,phone,latitude,longitude,neighborhood,logo,lastUpdated
```

### Product Type Values
- **RetailShake**: Hobbs Shake retail availability
- **RetailSauce**: Hobbs Sauce retail availability
- **Menu**: Restaurant partnership (in food or bottles with meals)

### Example Entry (CSV)
```csv
"Bottle Bar East","RetailShake,RetailSauce,Menu","1308 Frankford Ave, Philadelphia, PA 19125","https://maps.app.goo.gl/4VKgCGjFyxcTPMoN6","https://bottlebareast.com","+1 267-909-8867",39.96560624,-75.14223115,"Fishtown","BottleBarEastLogo.webp","11/3/2025"
```

### Example Entry (embedded JS)
```js
{ name: "Bottle Bar East", type: "RetailShake,RetailSauce,Menu", address: "1308 Frankford Ave, Philadelphia, PA 19125", googleMapsLink: "https://maps.app.goo.gl/4VKgCGjFyxcTPMoN6", website: "https://bottlebareast.com", phone: "+1 267-909-8867", latitude: 39.96560624, longitude: -75.14223115, neighborhood: "Fishtown", logo: "BottleBarEastLogo.webp", lastUpdated: "11/3/2025" }
```

## 🎨 Squarespace Integration

### Iframe Embedding
```html
<iframe src="https://saucemaster-web.github.io/HobbsSauce-map/index-squarespace-clean.html" 
        width="100%" height="800" frameborder="0" 
        title="Hobbs Sauce Locations Map">
</iframe>
```

### Chrome Local Network Prompt
- The map no longer fetches external CSV at runtime.
- Embedded data avoids Chrome's local network prompt heuristic.
- All external resources are limited to Leaflet (unpkg) and CARTO tiles.

### Content Security Policy
- `index.html` includes a CSP meta tag restricting sources:
   ```html
   <meta http-equiv="Content-Security-Policy" content="default-src 'self'; img-src 'self' data: https://unpkg.com https://*.cartocdn.com; style-src 'self' 'unsafe-inline' https://unpkg.com; script-src 'self' 'unsafe-inline' https://unpkg.com;">
   ```
- Adjust as needed if adding new domains or assets.

### Auto-Updates
- **GitHub integration** ensures Squarespace shows latest data
- **No manual code copying** required after initial setup
- **Consistent branding** with prefixed CSS classes
- **Performance optimized** for iframe context

## 🛠️ Customization

### Adding New Locations
1. Edit `index.html` and add a new object to `hobbsLocations`.
2. Include required fields: `name`, `type`, `address`, `latitude`, `longitude`.
3. Add `logo` file to `assets/` if available.
4. Keep `lastUpdated` current.
5. Optionally reflect changes in `data/hobbs_locations.csv`.
6. Commit and push changes.

### Styling Updates
- **CSS variables** for consistent theming
- **Component-based** styling approach
- **Mobile-first** responsive design
- **Brand colors**: Primary orange (#ff6600), secondary variants

### Feature Extensions
- **Filter system** easily expandable for new categories
- **Badge system** supports additional product types
- **Map controls** can be enhanced with plugins
- **Data sources** can be switched from CSV to API

## 🏪 Current Locations (14 Total)

### Retail + Restaurant Partners (3)
- Bottle Bar East - *All products*
- Liberty Kitchen PHL - *All products*  
- Yards Brewing Company - *All products*

### Retail Only (5)
- Palm Tree Market - *Shake & Sauce*
- Riverwards Produce Market (Fishtown) - *Shake & Sauce*
- Riverwards Produce Market (Old City) - *Shake & Sauce*
- Herman's Coffee - *Sauce only*

### Restaurant Partners (6)
- Bishop's Collar, Good Dog Bar, Jose Pistola's
- Sancho Pistola's, Pistola's Del Sur, Standard Tap
- Lucky's Last Chance Manayunk - *Also sells sauce*

## 🤝 Contributing

### Reporting Issues
- Use GitHub Issues for bugs or feature requests
- Include browser/device information for technical issues
- Provide specific location details for data corrections

### Code Contributions
1. Fork the repository
2. Create feature branch (`git checkout -b feature/new-feature`)
3. Make changes and test thoroughly
4. Submit pull request with clear description

## 📱 Browser Compatibility

- **Modern browsers**: Chrome, Firefox, Safari, Edge (latest 2 versions)
- **Mobile browsers**: iOS Safari, Chrome Mobile, Samsung Internet
- **Accessibility**: WCAG 2.1 AA compliant
- **Performance**: < 2MB total page weight, < 3s load time

## 📄 License

This project is part of the Hobbs Sauce brand. All rights reserved.

## 📞 Contact

For business inquiries or location updates, visit [Hobbs Sauce website] or contact through the map interface.

---

**Last Updated**: November 3, 2025  
**Version**: 2.0 - Restaurant Partner System  
**Maintained by**: Hobbs Sauce Team
