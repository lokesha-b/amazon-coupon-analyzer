Amazon Coupon Analyzer: Data Science Project

Project Overview

This project analyzes driver behavior regarding coupon acceptance while driving. Using data from the UCI Machine Learning repository collected via Amazon Mechanical Turk, we investigate what factors influence whether drivers accept coupons for various venues including restaurants, coffee houses, bars, and carry-out establishments.

Key Questions Answered
- What proportion of drivers accept different types of coupons?
- How do factors like age, passenger type, and visitation frequency affect acceptance?
- What are the key drivers of coupon acceptance behavior?
- How can businesses optimize their coupon targeting strategies?

Dataset Summary

-Total Observations: 12,684 driving scenarios
- Coupon Types: 5 categories
  - Coffee House (3,996 observations)
  - Restaurant(<$20) (2,798 observations) 
  - Carry out & Take away (2,395 observations)
  - Bar (2,014 observations)
  - Restaurant($20-$50) (1,481 observations)
- Data Source: UCI Machine Learning Repository via Amazon Mechanical Turk
- Target Variable: Y (1 = Accept coupon, 0 = Reject coupon)

Key Findings

Overall Acceptance Rates
| Coupon Type         | Acceptance Rate       | Count |
|-------------        |----------------       |--------------|
| Coffee House    | 65.0%             | 3,996     |
| Restaurant(<$20)    | ~55-60%               | 2,798     |
| Carry out & Take away | ~55-60%             | 2,395 |
| Restaurant($20-$50) | ~50-60%               | 1,481 |
| Bar             | 41.0%             | 2,014                 |
| Overall Average | 56.8%             | 12,684 |

Top Insights

1. Coffee House coupons dominate with 65% acceptance rate (24% above average)
2. Bar coupons underperform with 41% acceptance rate (16% below average)
3. Prior familiarity is the strongest predictor - frequent visitors are 3-4x more likely to accept
4. Social context matters significantly - passenger type influences acceptance patterns

Detailed Analysis Results

Data Quality & Preprocessing
- Missing Data Handling: 
  - Dropped 'car' column (99% missing values)
  - Mode imputation for other columns with missing data
  - Final clean dataset: 12,684 observations, 25 features

Bar Coupons Deep Dive Analysis

Key Findings:
- Acceptance Rate: 41.0% (vs 56.8% overall average)
- Visitation Frequency Impact:
  - Never visit bars: 19% acceptance
  - 1-3 times/month: 38% acceptance  
  - 4-8 times/month: 73% acceptance
  - >8 times/month: 78% acceptance

Multi-Factor Analysis:
1. Age + Visitation Pattern: Drivers >25 years who visit bars >1x/month show significantly higher acceptance
2. Social Context: Drivers with friends as passengers: 56% acceptance vs kids: 21% acceptance
3. Lifestyle Patterns: Combined conditions (bar visits + dining out + income) create strong predictive segments

Coffee House Coupons Independent Investigation

Breakthrough Findings:
- Highest performing coupon type at 65% acceptance rate
- Time-of-day sensitivity: 
  - 10AM: Peak acceptance (typical coffee break)
  - 2PM: Second peak (afternoon coffee)
  - 10PM: Lowest acceptance (late evening)
- Visitation frequency correlation: Similar to bars, frequent visitors show much higher acceptance
- Broader appeal: More family-friendly than bar coupons

Key Drivers of Coupon Acceptance

1. Prior Familiarity (Most Important Factor)
- Frequent visitors: 3-4x higher acceptance rates
- Never-visitors: Very low acceptance (15-25%)
- Strongest predictor across all coupon types

2. Social Context
- Friends as passengers: Higher acceptance for social venues
- Kids as passengers: Lower acceptance for adult-oriented venues (bars)
- Solo drivers: Moderate acceptance across all venue types

3. Time & Context Appropriateness
- Coffee coupons: Best during morning/afternoon hours
- Bar coupons: More accepted in evening/social contexts
- Restaurant coupons: Less time-sensitive

4. Demographic Patterns
- Age matters less than familiarity and context
- Income and occupation influence lifestyle patterns
- Marital status affects social context preferences

Visualizations Created

1. Coupon Types Distribution - Bar chart showing observation counts by coupon type
2. Temperature Distribution - Histogram with mean/median overlays
3. Bar Acceptance by Visitation Frequency - Grouped bar chart with acceptance rates
4. Age + Visitation Analysis - Comparison chart for target vs other groups
5. Multi-condition Analysis - Complex condition breakdown visualizations

Business Recommendations

Targeting Strategy
- Prioritize customers with existing visitation history to the venue type
- Use behavioral data over demographic data for targeting
- Consider time-of-day and passenger context in delivery timing

Venue-Specific Strategies

Coffee Houses
- Broad appeal across demographics
- Target morning hours (7AM-10AM) and afternoon (2PM-4PM)
- Social contexts (friends, partners) work better than family contexts
- Highest ROI and broadest reach of all coupon types

Bars
- Niche appeal requiring precise targeting
- Target frequent bar-goers (4+ visits/month)
- Evening hours and adult social contexts
- Avoid sending when children are passengers
- Younger drivers (21-26) with friends as passengers are prime targets

Restaurants
- Moderate appeal across demographics
- Family-friendly contexts work well
- Less time-sensitive than other venue types
- Steady, moderate performance across demographics

Context-Aware Delivery
- Avoid bar coupons when children are passengers
- Send coffee coupons during commute hours
- Consider destination context (work vs home vs leisure)

Technical Implementation

Libraries & Tools Used
- pandas - Data manipulation and analysis
- matplotlib - Data visualization
- seaborn - Statistical data visualization
- numpy - Numerical operations

Analysis Methods
- Statistical analysis with acceptance rate calculations
- Comparative analysis between demographic and behavioral segments
- Multi-condition analysis for complex pattern identification
- Hypothesis-driven approach with clear business implications


Business Impact

ROI Implications
- Coffee house coupons: Highest ROI and broadest reach
- Bar coupons: Require precise targeting but effective for right audience
- Restaurant coupons: Steady, moderate performance across demographics

Expected Improvements
- 3-4x higher conversion when targeting frequent visitors
- Significant cost savings through context-aware delivery
- Improved customer experience through relevant, timely offers


Conclusion

Coupon acceptance is highly predictable and driven by three key factors:
1. Prior familiarity with the venue type
2. Social context of the driving situation
3. Timing appropriateness for the venue type

By leveraging these insights, businesses can significantly improve their coupon targeting effectiveness and ROI through data-driven, context-aware marketing strategies.




How to run this repo ?

Clone or download this project
cd amazon-coupon-analyzer

Install all required dependencies
pip install -r requirements.txt

Open and run the notebook
jupyter notebook prompt.ipynb


Key Files
- `prompt.ipynb` - Complete analysis notebook 
- `data/coupons.csv` - Raw dataset 
- `README.md` - This documentation file

