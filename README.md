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
- **PapaParse v5.4.1** - CSV data parsing
- **CSS Grid & Flexbox** - Responsive layouts
- **Progressive Enhancement** - Works without JavaScript

### Data Management
- **CSV-based** location storage (`data/hobbs_locations.csv`)
- **GitHub Pages** hosting with automatic updates
- **Version control** through Git for all changes
- **Structured data** with validation and consistency

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
   ```bash
   git clone https://github.com/saucemaster-web/HobbsSauce-map.git
   cd HobbsSauce-map
   ```

2. **Open in browser**
   - Direct file access: Open `index.html` in browser
   - Local server: `python -m http.server 8000` or similar

3. **Make changes**
   - Edit CSV data in `data/hobbs_locations.csv`
   - Modify styling in the `<style>` sections
   - Update JavaScript functionality as needed

### Deployment
```bash
git add .
git commit -m "Description of changes"
git push origin main
```
Changes go live automatically via GitHub Pages (1-5 minute delay).

## 📊 Data Format

### CSV Structure
```csv
name,type,address,googleMapsLink,website,phone,latitude,longitude,neighborhood,logo,lastUpdated
```

### Product Type Values
- **RetailShake**: Hobbs Shake retail availability
- **RetailSauce**: Hobbs Sauce retail availability
- **Menu**: Restaurant partnership (in food or bottles with meals)

### Example Entry
```csv
"Bottle Bar East","RetailShake,RetailSauce,Menu","1308 Frankford Ave, Philadelphia, PA 19125","https://maps.app.goo.gl/4VKgCGjFyxcTPMoN6","https://bottlebareast.com","+1 267-909-8867",39.96560624,-75.14223115,"Fishtown","BottleBarEastLogo.webp","11/3/2025"
```

## 🎨 Squarespace Integration

### Iframe Embedding
```html
<iframe src="https://saucemaster-web.github.io/HobbsSauce-map/index-squarespace-clean.html" 
        width="100%" height="800" frameborder="0" 
        title="Hobbs Sauce Locations Map">
</iframe>
```

### Auto-Updates
- **GitHub integration** ensures Squarespace shows latest data
- **No manual code copying** required after initial setup
- **Consistent branding** with prefixed CSS classes
- **Performance optimized** for iframe context

## 🛠️ Customization

### Adding New Locations
1. Edit `data/hobbs_locations.csv`
2. Include required fields: name, type, address, coordinates
3. Add business logo to `assets/` folder if available
4. Commit and push changes

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
