# Airbnb NYC Pricing Optimization Project

**Course:** Data Science and AI for Business  
**Professor:** Dr. Chris Volinsky  
**Team:** Team M5  
**Members:** Princy Doshi, Ashutosh Agrawal, Om Thakur

---

## 📋 Project Overview

This project develops a machine learning-based pricing recommendation system for Airbnb property managers in New York City. Using data from Inside Airbnb, we predict optimal nightly rates to maximize revenue while maintaining healthy occupancy rates.

**Business Problem:** Property managers need to dynamically price their listings to balance occupancy and profitability.

**Solution:** ML models trained on 2,000+ NYC listings to predict competitive market rates based on property features, location, and demand indicators.

---

## 📁 Project Structure

```
airbnb-pricing-project/
│
├── data/
│   ├── listings.csv.gz           # Raw data (download from Inside Airbnb)
│   └── cleaned_dataset.csv        # Processed data (generated)
│
├── notebooks/
│   ├── 01_data_exploration.ipynb  # Initial data exploration
│   └── 02_master_analysis.ipynb   # Complete analysis pipeline
│
├── outputs/
│   ├── visualizations/
│   │   ├── neighborhood_overview.png
│   │   ├── price_distribution.png
│   │   ├── model_comparison.png
│   │   ├── actual_vs_predicted.png
│   │   ├── feature_importance.png
│   │   └── business_impact.png
│   │
│   ├── results/
│   │   ├── model_results.csv
│   │   ├── feature_importance.csv
│   │   ├── key_statistics.csv
│   │   ├── neighborhood_insights.csv
│   │   └── pricing_recommendations.csv
│   │
│   └── deliverables/
│       ├── Final_Report.pdf
│       └── Presentation_Slides.pptx
│
└── README.md (this file)
```

---

## 🚀 Quick Start Guide

### Step 1: Download Data
1. Go to: http://insideairbnb.com/get-the-data/
2. Find "New York City, New York, United States"
3. Download **listings.csv.gz**
4. Place in `data/` folder

### Step 2: Run Initial Exploration
```python
# Open 01_data_exploration.ipynb
# Run all cells to:
# - Load data
# - Explore neighborhoods
# - Decide on scope
```

### Step 3: Run Complete Analysis
```python
# Open 02_master_analysis.ipynb
# Update TARGET_NEIGHBORHOODS with your chosen areas
# Run all cells (takes 5-10 minutes)
# All outputs will be generated automatically
```

### Step 4: Use Generated Files
- Copy visualizations to presentation
- Use `key_statistics.txt` to fill report template
- Review `pricing_recommendations.csv` for business insights

---

## 🎯 Key Decisions Made

### 1. **Neighborhood Selection**
**Chosen:** [List your 3 neighborhoods]

**Rationale:**
- Geographic diversity (Manhattan, Brooklyn, Queens)
- Price point diversity (luxury, mid-range, budget)
- Sufficient data (500+ listings each)

### 2. **Filtering Criteria**
- **Room Type:** Entire home/apartment only
- **Minimum Reviews:** ≥5 (established listings)
- **Availability:** ≥30 days/year (active listings)
- **Price Range:** $50-$1,000/night (remove outliers)

**Result:** [X,XXX] listings retained ([XX]% of original)

### 3. **Feature Engineering**
Created 7 new features:
- `occupancy_proxy` - 365 - availability_365
- `occupancy_rate` - Occupancy proxy / 365
- `review_intensity` - Reviews per month × 12
- `instant_bookable_num` - Binary (1/0)
- `is_superhost` - Binary (1/0)
- `avg_review_score` - Composite of all review scores
- `amenities_count` - Number of amenities

### 4. **Model Selection**
Evaluated 5 models:
- Linear Regression (baseline)
- Ridge Regression (L2 regularization)
- Lasso Regression (L1 regularization)
- Random Forest (ensemble method)
- Gradient Boosting (sequential ensemble)

**Winner:** [Your best model]  
**Performance:** RMSE=$[XX.XX], R²=[0.XXX]

---

## 📊 Key Results

### Model Performance
- **RMSE:** $[XX.XX] - Average prediction error
- **R²:** [0.XXX] - Explains [XX]% of price variation
- **MAPE:** [X.X]% - Mean absolute percentage error

### Top Price Drivers
1. **[Feature 1]** - [XX]% importance
2. **[Feature 2]** - [XX]% importance
3. **[Feature 3]** - [XX]% importance
4. **[Feature 4]** - [XX]% importance
5. **[Feature 5]** - [XX]% importance

### Business Impact
- **Revenue Opportunity:** $[XXX,XXX] annually ([X]% increase)
- **Underpriced Properties:** [XX]% of portfolio
- **Average Opportunity:** $[XX]/night per underpriced listing

---

## 📈 Sample Insights

### By Neighborhood
| Neighborhood | Current Avg | Recommended Avg | Change |
|--------------|-------------|-----------------|--------|
| [Hood 1] | $[XXX] | $[XXX] | +$[XX] |
| [Hood 2] | $[XXX] | $[XXX] | +$[XX] |
| [Hood 3] | $[XXX] | $[XXX] | -$[XX] |

### Property Segments
- **Underpriced:** [XX]% → Increase rates by $[XX] avg
- **Optimal:** [XX]% → Maintain current rates
- **Overpriced:** [XX]% → Reduce rates by $[XX] avg

---

## 🎤 Presentation Structure

**Time:** 8-10 minutes

1. **Business Problem** (1 min)
   - Who we are, what decision we're making
   - Why dynamic pricing matters

2. **Data & Approach** (2 min)
   - Dataset scope
   - Key insights from EDA

3. **Model Results** (2 min)
   - Performance comparison
   - Best model selection
   - Feature importance

4. **Business Impact** (3 min)
   - Revenue opportunity quantified
   - Pricing recommendations
   - Implementation roadmap

5. **Q&A** (2 min)
   - Prepared for common questions

---

## 💡 Challenges & Solutions

### Challenge 1: Data Size
**Problem:** 40,000+ listings too large  
**Solution:** Filtered to 3 neighborhoods with diverse characteristics  
**Professor Feedback:** "Will need to narrow down... very large"

### Challenge 2: Missing Data
**Problem:** Missing bedrooms, bathrooms, review scores  
**Solution:** Median imputation for numeric, "Unknown" for categorical  
**Professor Feedback:** "Real data - will need to be cleaned"

### Challenge 3: Occupancy Data
**Problem:** No actual booking data available  
**Solution:** Used availability as proxy (365 - available days)  
**Future Work:** Integrate actual booking data for true revenue optimization

---

## 🔮 Future Enhancements

### Data
- [ ] Actual occupancy/booking data
- [ ] Events calendar (conferences, concerts)
- [ ] Weather data
- [ ] Transportation proximity
- [ ] Competitor pricing (real-time)

### Modeling
- [ ] Neural networks for complex patterns
- [ ] Time series for seasonality
- [ ] Multi-objective optimization (revenue + occupancy)
- [ ] Causal inference for price elasticity

### Product
- [ ] Real-time pricing dashboard
- [ ] Mobile app with alerts
- [ ] A/B testing framework
- [ ] Owner self-service portal

---

## 📚 References

1. **Data Source:** Inside Airbnb - http://insideairbnb.com/
2. **Course Textbook:** Provost & Fawcett (2013), *Data Science for Business*
3. **Libraries Used:** pandas, scikit-learn, matplotlib, seaborn
4. **Academic Papers:** [Add any you reference]

---

## 👥 Team Contributions

- **[Member 1]:** Data cleaning, EDA, report writing
- **[Member 2]:** Feature engineering, modeling, code development  
- **[Member 3]:** Business analysis, presentation, visualizations

*All team members contributed to project planning, analysis, and final deliverables.*

---

## ✅ Deliverables Checklist

### Code
- [x] Data loading and exploration notebook
- [x] Complete analysis pipeline
- [x] Well-commented, reproducible code
- [x] All visualizations generated

### Report (Due: [Date])
- [ ] Business understanding section
- [ ] Data preparation documentation
- [ ] Exploratory data analysis
- [ ] Modeling methodology
- [ ] Results and evaluation
- [ ] Business impact quantified
- [ ] Deployment considerations
- [ ] Future work discussed
- [ ] Proofread and formatted
- [ ] Exported as PDF

### Presentation (Due: [Date] midnight before)
- [ ] 10 slides maximum
- [ ] 8-10 minute timing verified
- [ ] All team members have speaking parts
- [ ] Visualizations clear and large fonts
- [ ] Q&A preparation
- [ ] Uploaded to Google Drive
- [ ] Tested in classroom

### Submission
- [ ] Report PDF submitted
- [ ] Slides uploaded on time
- [ ] Code/notebooks included
- [ ] Team evaluation form completed

---

## 🎓 Alignment with Course Rubric

### Report (60% of project grade)

**Business Understanding** ✅
- Clear problem statement
- Decision framework defined
- Benefits quantified

**Data Preparation** ✅
- Cleaning process documented
- Filtering rationale explained
- Feature engineering justified

**Exploratory Data Analysis** ✅
- Multiple visualizations
- Key insights identified
- Domain expertise applied

**Modeling** ✅
- Multiple algorithms compared
- Appropriate evaluation metrics
- Best model selected with rationale

**Evaluation** ✅
- Metrics interpreted
- Error analysis performed
- Limitations discussed

**Business Impact** ✅
- ROI quantified ($XXX,XXX revenue increase)
- Implementation plan provided
- Risks identified and mitigated

**Organization** ✅
- Structured narrative
- Professional formatting
- Clear conclusions

### Presentation (30% of project grade)

**Business Setup** ✅
- Clear problem motivation
- Role-playing as decision makers

**Effectiveness** ✅
- Engaging visuals
- Clear narrative arc
- Proper timing (8-10 min)

**Model Results** ✅
- Appropriate evaluation
- Clear interpretation
- Feature importance explained

**Impact Discussion** ✅
- Quantified benefits
- Implementation roadmap
- Future directions

---

## 📝 Notes

### What We Learned
- Real-world data is messy (professor was right!)
- Feature engineering > algorithm selection
- Business context crucial for interpretation
- Communication as important as technical accuracy

### What Worked Well
- Structured pipeline approach
- Early neighborhood scoping
- Comprehensive EDA
- Clear business framing

### What We'd Do Differently
- Start data cleaning earlier
- More time on feature engineering
- Test multiple neighborhood combinations
- Earlier presentation practice

---

## 📄 License & Data Usage

**Data:** Inside Airbnb data is made available under Creative Commons CC0 1.0 Universal License.

**Project:** Created for educational purposes as part of NYU Stern Data Science course.

**Academic Integrity:** This project follows NYU Stern's Academic Integrity policies and Student Code of Conduct. All work is original, with proper attribution to data sources and references.

---

## 🎉 Acknowledgments

- **Professor Chris Volinsky** for project guidance and feedback
- **Inside Airbnb** for providing open data
- **Teaching assistants** for technical support
- **Team members** for collaboration and hard work

---

**Last Updated:** [Date]  
**Version:** 1.0  
**Status:** ✅ Ready for submission

---

## Contact

For questions about this project:
- Team: pd
- Course: GB-2336/3336 - Data Science and AI for Business
- Institution: NYU Stern School of Business