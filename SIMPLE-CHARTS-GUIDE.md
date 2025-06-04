# owid-simple-charts

**The missing user-friendly interface for OWID's world-class data visualization library**

*Status: v0.1 - Just getting started!*

## What is this?

This project aims to solve a simple problem: **OWID's grapher is amazing, but way too complex for most people to use**.

[Our World in Data](https://ourworldindata.org) has built one of the best interactive data visualization libraries on the web. Their charts are gorgeous, responsive, and handle everything from line charts to world maps. The problem? Using it requires:

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

## Why OWID's grapher rocks

OWID didn't just build another charting library. They solved real problems:

- **Responsive by default** - Works perfectly on mobile and desktop
- **Handles missing data gracefully** - No broken charts from incomplete datasets
- **Built for storytelling** - Annotations, sources, and context built-in
- **Accessibility first** - Screen reader friendly, keyboard navigation
- **Time series animations** - Play through years of data smoothly
- **World map support** - Choropleth maps with built-in country data
- **Professional styling** - Looks like it belongs in a research paper

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

## Getting started

*Documentation coming soon as we build this out!*

### For developers

```bash
# Clone and explore the original OWID codebase
git clone https://github.com/SokolskyNikita/owid-simple-charts.git
cd owid-simple-charts

# The magic happens in these packages:
# packages/@ourworldindata/grapher - The core visualization library
# packages/@ourworldindata/core-table - Data handling and transforms
```

### Current status

- [x] Research and understand OWID's architecture
- [x] Identify the core packages we need
- [x] Create this repository and documentation
- [ ] Build minimal CSV → Chart proof of concept
- [ ] Create web interface for chart configuration
- [ ] Add embed URL generation
- [ ] Deploy hosting infrastructure

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

Upload that file, and get an interactive line chart showing life expectancy trends.

## Why not just use Chart.js or D3?

Good question! Those are excellent libraries, but OWID's grapher handles things they don't:

- **Automatic entity selection** - Choose which countries to show
- **Time scrubbing** - Slide through years of data
- **Smart labeling** - Automatically positions labels to avoid overlap
- **Missing data handling** - Graceful degradation when data points are missing
- **Source attribution** - Built-in citation and source management
- **Responsive legends** - Adapts to screen size and data complexity

## Contributing

This is v0.1 - we're just getting started! If you're interested in:

- Making data visualization more accessible
- React/TypeScript development
- Data pipeline architecture
- UX design for data tools

Drop a comment in the issues or submit a PR.

## License

MIT (same as OWID's original project)

---

*This project is not officially affiliated with Our World in Data, but we're huge fans of their work and hope to make their excellent tools more accessible to everyone.* 