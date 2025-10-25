# Click vs. Conversions: A Funnel Deep Dive

## Executive Summary
This report analyzes social media ad performance dataset from [Kaggle by alperenmyung](https://www.kaggle.com/datasets/alperenmyung/social-media-advertisement-performance/data)  We will try to identify drop-off points in the customer conversion funnel. The analysis reveals one primary finding:

**Key Finding:** The campaign's Impression to Click step is exceptionally strong, with a 98.21% click-through rate. The primary "leak" and area for optimization is the Click to Purchase step, where 81.52% of users who click the ad fail to make a purchase.

The drop-off is not caused by poor audience targeting because the age or gender segments perform equally well. Instead, the drop-off is strongly correlated three factors:
1. **Platform:** Instagram converts at half the rate of Facebook
2. **Creative:** Video Ads are the worst performing format
3. **Geograpy:** Key Markets like Mexico and Japan convert at much higher rates that France or Australia

## Part 1: The Overall Funnel (The "What)
First, we established the main conversion funnel by counting the number of *unique users* who reached each key step. The logical path from the data is:
**Impression → Click → Purchase**
- **Impressions:** 9,950 unique users saw an ad
- **Clicks:** 9,772 of those users clicked an ad
-  **Purchases:** 1,806 of those users made a purchase
The table below details the conversion and, more importantly, the drop-off rates between these steps

| **Step** | **Users** | **Step-to-Step CR (%)** | **Drop-off (Users)** | **Drop-off (%)** |
|--|--|--|--|--|
| Impression | 9,950 | 100% | 0 | 0% |
| Click | 9,772 | 98.21% | 178 | 1.79% |
| Purchase | 1,806 | 18.48% | 7,966 | 81.52% |

The data confirms that our ads are highly effective at capturing attention but are failing to convert that attention into sales.

To illustrate this user journey, here are two visualizations we can make:
1. **Funnel Bar Chart**

![](https://github.com/kaylaisya/SocMed-Ad-Funnel-Analysis/blob/main/overall_funnel_chart.png)

This chart shows the total of unique users who reached each step. It is useful for quickly grasping the *magnitude* of the audience at each step and visually identifying the biggest drop-off, which is clearly between the "Click" and "Purchase" steps.

2.  **Funnel Flowchart**

![](https://github.com/kaylaisya/SocMed-Ad-Funnel-Analysis/blob/main/funnel_flowchart.png)

This flowchart provides a more detailed, step-by-step view. The nodes show the user counts, while the arrows connecting them show the exact **conversion rate** (who moved on) and the **drop-off rate** (who was lost). This visualization pinpoints the 81.52% drop-off as the primary problem to be solved.

##  Part 2: Segmented Analysis (The "Why")
To understand *why* 81.52% of users drop-off after clicking, the funnel was segmented by platform, ad type, and user demographics.

### Finding 1: Facebook Outperforms Instagram by ~2x
The choice of platform is a major factor. While both platforms get clicks, Facebook is nearly twice as effective at turning those clicks into sales.

- **Facebook:** Achieves a **12.52%** Click-to-Purchase rate
- **Instagram:** Only achieves a **6.83%** Click-to-Purchase rate

| **Ad Platform** | **Impressions** | **Clicks** | **Purchases** | **Imp_to_Click_CR (%)** | **Click_to_Purchase_CR (%)** | **Overall_CR (%)** |
| -- | -- | -- | -- | -- | -- | -- |
| **Facebook** | 9,950 | 9,156 | 1,146 | 92.02% | **12.52%** | 11.52% |
| **Instagram** | 9,950 | 7,633 | 521 | 76.71% | **6.83%** | 5.24% |

### Finding 2: Video Ads are the Worst Performing Format
The creative format of your ad has a significant impact on conversion. **Stories** are the most effective format for turning a click into a sale, while **Video Ads** perform the worst.

- **Stories: 6.52%** Click-to-Purchase Rate
- **Video: 3.34%** Click-to-Purchase Rate

| **Ad Type** | **Impressions** | **Clicks** | **Purchases** | **Imp_to_Click_CR (%)** | **Click_to_Purchase_CR (%)** | **Overall_CR (%)** |
| -- | -- | -- | -- | -- | -- | -- |
| **Stories** | 9,950 | 7,179 | 468 | 72.15% | **6.52%** | 4.70% |
| **Carousel** | 9,949 | 6,371 | 329 |64.04% | **5.16%** | 3.31% |
| **Image** | 9,948 | 6,483 | 295 | 65.17% | **4.55%** | 2.97% |
| **Video** | 9,908 | 4,853 | 162 | 48.98% | **3.34%** | 1.64% |

### Finding 3: Geographic Performance Varies
While basic demographics (age/gender) are consistent, *geography* is a significant variable. Users in Mexico and Japan convert from Click-to-Purchase at a rate of ~22.7%, while users in France convert at only 15.6%. This suggests that landing pages or offers may resonate differently across cultures

| **Country** | **Impressions** | **Clicks** | **Purchases** | **Imp_to_Click_CR (%)** | **Click_to_Purchase_CR (%)** | **Overall_CR (%)** |
| -- | -- | -- | -- | -- | -- | -- |
| United States | 3014 | 2959 | 568 | 98.18% | **19.20%** | 18.85% |
| Mexico | 512 | 505 | 115 | 98.63% | **22.77%** | 22.46% |
| Japan | 490 | 479 | 109 | 97.76% | **22.76%** | 22.46% |
| United Kingdom | 1510 | 1482 | 261 | 98.15% | **17.61%** | 17.28% |
| Canada | 1000 | 982 | 177 | 98.20% | **18.02%** | 17.70% |
| Brazil | 607 | 597 | 107 | 98.35% | **17.92%** | 17.63% |
| Germany | 823 | 811 | 141 | 98.54% | **17.39%** | 17.13% |
| Australia | 716 | 702 | 115 | 98.04% | **16.38%** | 16.06% |
| France | 376 | 371 | 58 | 98.67% | **15.63%** | 15.43% |

### Finding 4: Audience Demopgraphics (Age/Gender) are Not the Problem
In contrast to geography, the analysis of user demographics shows that the drop-off is **not** related to a specific age group or gender. The Click-to-Purchase rate is remarkably consistent across all segments (16-19%)

This is good news, because it means the audience targeting is likely correct. The problem lies with the **creative strategy, platform choice,** and **geographic/cultural** alignment
 
## Summary & Actionable Reccomendations
1. **The Problem:** The funnel's main leak is **after the click**, where 81,52% of interested users are lost
2. **The Cause:** This problem is concentrated in two areas:
	- **Platform: Instagram** converts clicks to sales at half the rate of Facebook
	- **Creative: Video Ads** are the worst performing format, converting at nearly half the rate of Stories
	- **Geography: France and Australia** show significantly lower conversion rates that top markets like Mexico and Japan
3. **Action Plan:**
	- **Audit the Post-Click Experience:** Immediately review the landing pages for **Instagram** and **Video ads**, and low-performing coutries like **France**
		- *Hypothesis 1:* The page is not mobile-optimized, causing Instagram users to bounce
		- *Hypothesis 2:* The landing page does no match the promise/content of the video ad, causing confusion
		- *Hypothesis 3:* The offer or landing page is not culturally or linguistically optimized for France
	- **Optimize & Re-allocate:** 
		-  A/B Test new landing pages for vide ads or replace them with **Stories** and **Carousel** formats that are proven to convert better
		- Shift budget from Instagram to the proven winner, **Facebook**
		-  Analyze the difference between the **Mexico/Japan** and **France/Asutralia** campaigns
	- **Investigate Top Markets:** Explore what makes the **Mexico and **Japan** landing pages so effective. Can those learning be applied to other regions?

