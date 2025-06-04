# 🚀 owid-simple-charts

**The missing user-friendly interface for OWID's world-class data visualization library**

*Status: v0.1 - Just getting started!*

> 📖 **Looking for technical docs?** See the [original OWID README](README.md) for developer setup, architecture details, and contribution guidelines.

## What is this?

This project solves a simple problem: **OWID's grapher is amazing, but way too complex for most people to use**.

[Our World in Data](https://ourworldindata.org) built one of the best interactive data visualization libraries on the web. Their charts are gorgeous, responsive, and handle everything from line charts to world maps. The problem? Using it requires:

- Docker setup
- MySQL database 
- 20-minute initialization process
- Deep technical knowledge
- Understanding their complex data pipeline

## What we're building

A simple web interface where you can:

1. **Upload a CSV file** (drag & drop)
2. **Configure your chart** (choose chart type, set axes, pick colors)  
3. **Get an embed URL** (host it yourself or use our hosting)

Think "Plotly for OWID charts" or "Chart.js but with OWID's power."

## Why OWID's grapher rocks (and why we're not rebuilding it)

OWID didn't just build another charting library. They solved real problems that most visualization tools ignore:

- **Responsive by default** - Works perfectly on mobile and desktop
- **Handles missing data gracefully** - No broken charts from incomplete datasets
- **Built for storytelling** - Annotations, sources, and context built-in
- **Accessibility first** - Screen reader friendly, keyboard navigation
- **Time series animations** - Play through years of data smoothly
- **World map support** - Choropleth maps with built-in country data
- **Professional styling** - Looks like it belongs in a research paper
- **Smart labeling** - Automatically positions labels to avoid overlap
- **Entity selection** - Choose which countries/regions to show
- **Source attribution** - Built-in citation and source management

## The technical approach

Instead of rebuilding everything, we're extracting OWID's core `@ourworldindata/grapher` package and wrapping it in a simple React interface.

**Current OWID workflow:**
```
Complex Admin Interface → Database → Multi-step Pipeline → Chart
```

**Our workflow:**
```
CSV Upload → Simple UI → Chart → Embed URL
```

## Quick start (for end users)

*Coming soon! We're building this now.*

1. Visit our web app
2. Drag & drop your CSV file
3. Configure your chart
4. Copy the embed code

## Sample data format

We're aiming to support simple CSV files like this:

```csv
Country,Year,Life_Expectancy
World,1990,64.2
World,2000,67.2
World,2010,70.0
World,2020,72.6
USA,1990,75.4
USA,2000,76.8
USA,2010,78.5
USA,2020,78.9
```

Upload that file → Get an interactive line chart showing life expectancy trends with:
- Entity selector (toggle countries on/off)
- Time scrubber (slide through years)
- Hover tooltips with exact values
- Mobile-responsive design
- Export options (PNG, SVG, CSV)

## Why not just use Chart.js, D3, or Plotly?

Great question! Those are excellent libraries, but OWID's grapher handles edge cases they don't:

| Feature | Chart.js | D3.js | Plotly | OWID Grapher |
|---------|----------|-------|--------|-------------|
| Responsive design | Basic | Manual | Good | Excellent |
| Missing data handling | Poor | Manual | Good | Excellent |
| Entity selection | None | Manual | Basic | Advanced |
| Time animations | None | Manual | Basic | Smooth |
| World maps | None | Complex | Basic | Professional |
| Source attribution | None | Manual | None | Built-in |
| Accessibility | Basic | Manual | Good | Excellent |

## Development roadmap

### Phase 1: Proof of Concept ✨ *← We are here*
- [x] Research OWID architecture
- [x] Identify core packages
- [x] Create repository and documentation
- [ ] Build minimal CSV → Chart PoC
- [ ] Validate approach with sample data

### Phase 2: Core Interface
- [ ] File upload with validation
- [ ] Chart type selection (Line, Bar, Scatter, Map)
- [ ] Axis configuration
- [ ] Color scheme picker
- [ ] Entity filtering

### Phase 3: Advanced Features
- [ ] Chart annotations
- [ ] Custom styling options
- [ ] Embed URL generation
- [ ] Export functionality

### Phase 4: Platform
- [ ] User accounts
- [ ] Chart galleries
- [ ] Collaboration features
- [ ] Hosting infrastructure

## For developers

Want to contribute? Here's how to get started:

### Understanding the codebase
The magic happens in these packages:
- `packages/@ourworldindata/grapher` - Core visualization library
- `packages/@ourworldindata/core-table` - Data handling ("Pandas for TypeScript")
- `packages/@ourworldindata/utils` - Shared utilities

### Local development
```bash
# Clone this repository
git clone https://github.com/SokolskyNikita/owid-simple-charts.git
cd owid-simple-charts

# For full OWID setup, see the main README.md
# For simple chart development, we'll create a standalone Next.js app
```

### Contributing
This is v0.1 - we're just getting started! Areas where we need help:

- **React/TypeScript development** - Building the user interface
- **Data pipeline architecture** - CSV parsing and transformation
- **UX design** - Making data visualization accessible
- **Documentation** - Guides and tutorials
- **Testing** - Ensuring reliability across datasets

## Frequently asked questions

**Q: Is this affiliated with Our World in Data?**
A: No, this is an independent project. We're huge fans of their work and hope to make their excellent tools more accessible.

**Q: Why fork instead of contribute upstream?**
A: OWID's tools are designed for their specific needs (research organization with technical team). We're building for a different audience (anyone who wants great charts).

**Q: Will this compete with OWID?**
A: Not at all! We're expanding their reach. More people using OWID-quality visualizations = more people appreciating good data visualization.

**Q: What's the business model?**
A: TBD. Possibly freemium hosting, or just open source forever. Our goal is accessibility, not profit.

## License

MIT (same as OWID's original project)

---

**🤝 Ready to help make data visualization accessible to everyone?**

- 💬 [Join the discussion](https://github.com/SokolskyNikita/owid-simple-charts/discussions)
- 🐛 [Report issues](https://github.com/SokolskyNikita/owid-simple-charts/issues)
- 🚀 [Submit pull requests](https://github.com/SokolskyNikita/owid-simple-charts/pulls)

*This project is not officially affiliated with Our World in Data, but we're huge fans of their work.* 