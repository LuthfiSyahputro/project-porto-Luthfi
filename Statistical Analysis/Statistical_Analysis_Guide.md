# 📊 STATISTICAL ANALYSIS - COMPLETE REPORT

**Date:** February 6, 2026  
**Analyst:** Data Science Team  
**Tests Analyzed:** 5 A/B Tests

---

## 🎯 EXECUTIVE SUMMARY

Analisis statistik mendalam telah dilakukan terhadap 5 A/B test dengan fokus pada:
- **Effect Size Analysis** (Cohen's d)
- **Statistical Power** & Required Sample Size
- **Confidence Intervals** (95% & 99%)
- **Segmentation Analysis** (Device, Browser, Region)
- **Time Series & Trend Analysis**

### Quick Decision Guide

| Test | Decision | Confidence | Key Metric Impact |
|------|----------|-----------|-------------------|
| Test 1: Menu Layout | ❌ **REJECT** dropdown menu | 🟢 Very High | Revenue: -10.5%, Cart: -10.3% |
| Test 2: Novelty Slider | ⚠️ **CAUTIOUS ACCEPT** | 🟡 Medium | Revenue: +5.8% (needs adjustment) |
| Test 3: Product Sliders | ⚠️ **NEEDS ANALYSIS** | 🟡 Low | Multiple imbalances |
| Test 4: Reviews | ❌ **NO EFFECT** | 🟢 High | Cart: +0.5% (not significant) |
| Test 5: Search Engine | ✅ **ACCEPT** Algolia | 🟢 High | Cart: +1.5% |

---

## 📈 TEST 1: MENU LAYOUT

### Setup
- **Control:** A_horizontal_menu (3,500 users)
- **Treatment:** B_dropdown_menu (3,500 users)
- **Duration:** March 1-7, 2021 (7 days)
- **Primary Metrics:** pages_viewed, added_to_cart, bounced, revenue

---

### 🔍 DETAILED METRIC ANALYSIS

#### 1. **Revenue** ⭐⭐⭐
```
Control (A):    $3.49 ± 2.55
Treatment (B):  $3.13 ± 2.24
Difference:     -$0.37 (-10.51%)

95% CI:         [-$0.48, -$0.25]
99% CI:         [-$0.53, -$0.20]

Cohen's d:      -0.153 (negligible, but practically significant)
P-value:        < 0.001 ***
Power:          100% ✅

Interpretation: Dropdown menu SIGNIFICANTLY hurts revenue
```

**Apa artinya?**
- Dropdown menu menyebabkan penurunan revenue rata-rata $0.37 per user
- Dengan 95% confidence, penurunan antara $0.25 - $0.48
- Meskipun effect size "negligible", dampak bisnis SANGAT BESAR (10.5%)
- Power 100% artinya kita SANGAT YAKIN hasil ini bukan kebetulan

**Business Impact:**
- Jika 1 juta users/month → Loss $370,000/month
- Annual impact: **-$4.4 juta/tahun**

---

#### 2. **Add to Cart Rate** ⭐⭐⭐
```
Control (A):    96.2% (0.962)
Treatment (B):  86.2% (0.862)
Difference:     -10.0 percentage points (-10.34%)

95% CI:         [-11.7%, -9.0%]
99% CI:         [-12.3%, -8.4%]

Cohen's d:      -0.357 (small effect)
P-value:        < 0.001 ***
Power:          100% ✅

Interpretation: Dropdown menu DRASTICALLY reduces cart additions
```

**Apa artinya?**
- Dari 100 users, dropdown menu kehilangan ~10 cart additions
- Effect size "small" tapi dampak praktis SANGAT BESAR
- Ini adalah RED FLAG terbesar dari test ini

**Funnel Impact:**
```
Horizontal Menu (A):  96.2% add to cart
Dropdown Menu (B):    86.2% add to cart
                      -----
Loss:                 -10 percentage points

Kalau 1,000 visitors:
- Horizontal: 962 add to cart
- Dropdown:   862 add to cart
- LOST:       100 potential customers!
```

---

#### 3. **Pages Viewed**
```
Control (A):    2.19 pages
Treatment (B):  2.15 pages
Difference:     -0.04 pages (-2.01%)

95% CI:         [-0.079, -0.009]
Cohen's d:      -0.059 (negligible)
P-value:        0.013 *
Power:          70% ⚠️

Interpretation: Slight decrease, marginal significance
```

**Apa artinya?**
- Power hanya 70%, idealnya 80%+
- Butuh 4,451 user per grup untuk power 80%
- Efek ada tapi kecil, tidak terlalu penting

---

#### 4. **Bounce Rate**
```
Control (A):    43.4%
Treatment (B):  44.5%
Difference:     +1.1 percentage points (+2.63%)

95% CI:         [-1.2%, +3.5%]
Cohen's d:      0.023 (negligible)
P-value:        0.336 (NOT significant)
Power:          16% ❌

Interpretation: NO significant difference in bounce rate
```

**Apa artinya?**
- Test SANGAT underpowered (16%)
- Butuh 29,615 user per grup untuk detect effect ini
- Tidak ada bukti perbedaan bounce rate

---

### 📱 SEGMENTATION ANALYSIS

Analisis per segmen untuk metric **pages_viewed**:

#### Device Type
```
Desktop:  -1.53% (p=0.227) - Not significant
Mobile:   -2.26% (p=0.039) ✅ - Significant!
Tablet:   -3.13% (p=0.393) - Not significant
```

**Key Insight:** Mobile users PALING TERPENGARUH oleh dropdown menu!

#### Browser
```
Chrome:   -2.55% (p=0.026) ✅ - Significant
Edge:     -3.96% (p=0.105) - Not significant  
Firefox:  +1.44% (p=0.492) - Not significant (positive!)
Safari:   -2.16% (p=0.183) - Not significant
```

**Key Insight:** Chrome users (mayoritas) significantly affected. Firefox users malah sedikit naik (tapi tidak signifikan).

#### Region
```
All regions show negative trend, none significant individually
Range: -1.22% to -2.35%
```

**Key Insight:** Effect konsisten across regions - ini BUKAN regional issue.

---

### 📈 TIME SERIES ANALYSIS

```
Control Trend Correlation:    -0.121 (slight decline over time)
Treatment Trend Correlation:  +0.389 (moderate increase over time)

⚠️ TREND DETECTED!
```

**Apa artinya?**
- Control group (horizontal menu) stabil/slight decline
- Treatment group (dropdown) showing improvement trend
- **POSSIBLE LEARNING EFFECT:** Users adapting to dropdown?
- **RECOMMENDATION:** Monitor for 2-3 more weeks to confirm

---

### 🎯 CONVERSION FUNNEL

```
Stage: Add to Cart
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Horizontal Menu (A):  96.2% ████████████████████░
Dropdown Menu (B):    86.2% ███████████████▓▓▓▓▓

LOSS: -10 percentage points
```

Ini adalah MAJOR LEAK dalam funnel!

---

### 💡 FINAL RECOMMENDATION - TEST 1

```
╔══════════════════════════════════════════════════════╗
║  🔴 STRONGLY RECOMMEND: REJECT DROPDOWN MENU         ║
║                                                      ║
║  Confidence Level: ⭐⭐⭐⭐⭐ (Very High)                ║
║  Statistical Significance: p < 0.001 (Highly sig)   ║
║  Business Impact: -$4.4M annual revenue             ║
║  Power: 100% (Extremely robust)                     ║
╚══════════════════════════════════════════════════════╝
```

**Action Items:**
1. ✅ Keep horizontal menu (current)
2. ❌ Do NOT implement dropdown menu
3. 🔍 Investigate WHY dropdown performs so badly
   - Possible issues: harder navigation, hidden options, mobile UX
4. 💡 Consider alternative navigation improvements

---

## 📊 TEST 2: NOVELTY SLIDER

### Setup
- **Control:** A_manual_novelties (8,000 users)
- **Treatment:** B_personalized_novelties (8,000 users)
- **Duration:** March 9-21, 2021 (13 days)
- **Primary Metric:** novelty_revenue

---

### 🔍 METRIC ANALYSIS

#### **Novelty Revenue** ⭐⭐
```
Control (A):    $4.23 ± 2.45
Treatment (B):  $4.48 ± 2.60
Difference:     +$0.25 (+5.81%)

95% CI:         [+$0.17, +$0.32]
99% CI:         [+$0.14, +$0.36]

Cohen's d:      0.097 (negligible effect size)
P-value:        < 0.001 *** (highly significant)
Power:          100% ✅

Interpretation: Personalization INCREASES novelty revenue
```

**Apa artinya?**
- Personalized recommendations meningkatkan revenue $0.25 per user
- Effect size kecil (Cohen's d = 0.10) TAPI statistically very significant
- Confidence interval TIDAK cross zero → effect REAL
- Power 100% → results HIGHLY reliable

**Business Impact:**
- 1 juta users/month → +$250,000/month
- Annual impact: **+$3 juta/tahun**

**⚠️ CRITICAL CAVEAT:**
```
Covariate Imbalance Detected:
- products_added_from_novelties: p < 0.000008

This means groups were NOT perfectly balanced!
TRUE EFFECT might be different after adjustment.
```

---

### 📱 SEGMENTATION ANALYSIS

#### Device Type ⭐
```
Desktop:  +4.78% (p=0.001) ✅✅
Mobile:   +5.96% (p<0.001) ✅✅✅
Tablet:   +12.75% (p=0.003) ✅✅✅ BEST!
```

**MAJOR INSIGHT:** Tablet users benefit MOST from personalization!

**Why tablets?**
- Larger screen → better showcase
- Typical usage: browsing/shopping
- More time per session

**Business Strategy:**
- PRIORITIZE personalization on tablet
- Consider tablet-specific UI optimization

---

#### Browser
```
Chrome:   +6.21% (p<0.001) ✅✅✅
Edge:     +6.60% (p=0.029) ✅✅
Firefox:  +3.92% (p=0.111) ~ (borderline)
Safari:   +5.78% (p=0.002) ✅✅
```

**Insight:** Effect consistent across browsers (good sign!)

---

#### Region
```
Osijek:   -0.01% (p=0.999) - NO EFFECT
Other:    +6.62% (p=0.002) ✅✅
Rijeka:   +2.85% (p=0.233) ~
Split:    +6.83% (p=0.002) ✅✅  
Zagreb:   +7.77% (p<0.001) ✅✅✅ BEST!
```

**MAJOR FINDING:** 
- Zagreb users benefit MOST (+7.77%)
- Osijek shows NO benefit (interesting!)

**Possible explanations:**
- Different shopping behavior?
- Different product preferences?
- Market maturity differences?

**Action:** Investigate Zagreb vs Osijek user behavior

---

### 📈 TIME SERIES ANALYSIS

```
Control Trend:    +0.410 (moderate positive trend)
Treatment Trend:  -0.237 (slight negative trend)

⚠️ CONCERNING PATTERN!
```

**Apa artinya?**
- Control group IMPROVING over time (why?)
- Treatment group DECLINING slightly (novelty wearing off?)

**Possible explanations:**
1. **Seasonal effects** - product mix changing
2. **Novelty effect fading** - personalization less exciting over time
3. **Learning algorithm** - needs more time to optimize

**RECOMMENDATION:** 
- Monitor for 4-6 more weeks
- Check if treatment stabilizes
- Might need algorithm tuning

---

### 💡 FINAL RECOMMENDATION - TEST 2

```
╔══════════════════════════════════════════════════════╗
║  ⚠️  CAUTIOUS ACCEPTANCE WITH CONDITIONS              ║
║                                                      ║
║  Confidence Level: ⭐⭐⭐ (Medium-High)                 ║
║  Raw Effect: +5.81% (p<0.001)                       ║
║  Covariate Imbalance: YES (Critical)                ║
║  Temporal Trend: Concerning                         ║
╚══════════════════════════════════════════════════════╝
```

**Next Steps:**
1. 🔧 Apply CUPED adjustment for covariate imbalance
2. 📊 Re-analyze with adjusted data
3. 📈 Monitor for 4 more weeks (temporal stability)
4. 🎯 If still positive after adjustment → IMPLEMENT
5. 💡 Focus rollout on: Tablets, Zagreb, Chrome users

**DO NOT implement yet** - wait for adjusted analysis!

---

## 📊 TEST 4: REVIEWS

### Setup
- **Control:** A_no_featured_reviews (21,000 users)
- **Treatment:** B_featured_reviews (21,000 users)
- **Duration:** April 7 - May 11, 2021 (35 days)
- **Primary Metric:** added_to_cart

---

### 🔍 METRIC ANALYSIS

#### **Add to Cart Rate**
```
Control (A):    82.7%
Treatment (B):  83.1%
Difference:     +0.44 percentage points (+0.53%)

95% CI:         [-0.28%, +1.16%]
99% CI:         [-0.47%, +1.35%]

Cohen's d:      0.012 (negligible)
P-value:        0.233 (NOT significant)
Power:          22% ❌ (Very low!)

Interpretation: NO significant effect detected
```

**Apa artinya?**
- Featured reviews TIDAK memberikan dampak yang terukur
- Confidence interval MENCAKUP ZERO → tidak yakin arah effect
- Power sangat rendah (22%) → test underpowered
- Butuh 115,973 users per grup untuk detect effect size ini dengan 80% power

---

### 📱 SEGMENTATION ANALYSIS

**Semua segmen menunjukkan NO SIGNIFICANT EFFECT:**

```
Device Type:
- Desktop:  +0.77% (p=0.274)
- Mobile:   +0.32% (p=0.593)
- Tablet:   +0.91% (p=0.658)

Browser:
- Chrome:   +0.39% (p=0.533)
- Edge:     +0.41% (p=0.774)
- Firefox:  -0.39% (p=0.736)
- Safari:   +1.39% (p=0.116)

Region:
- All regions: Not significant
```

**Insight:** Effect nihil across ALL segments

---

### 🎯 CONVERSION FUNNEL

```
A (No Reviews):     82.7% ████████████████▓
B (With Reviews):   83.1% ████████████████▓

Difference: +0.4% (negligible)
```

---

### 💡 FINAL RECOMMENDATION - TEST 4

```
╔══════════════════════════════════════════════════════╗
║  ❌ REJECT FEATURED REVIEWS FEATURE                   ║
║                                                      ║
║  Confidence Level: ⭐⭐⭐⭐ (High)                       ║
║  Effect: +0.53% (NOT significant, p=0.233)          ║
║  Power: 22% (Underpowered, but effect too small)    ║
║  Business Value: NONE                               ║
╚══════════════════════════════════════════════════════╝
```

**Action Items:**
1. ❌ Do NOT implement featured reviews
2. 💰 Save engineering resources
3. 🔍 Consider alternative review strategies:
   - Review highlighting algorithms
   - Social proof elements
   - User-generated content integration

**Why reject despite low power?**
- Even if true effect exists, it's < 1% (not worth effort)
- 35 days testing, 42K users → sufficient exposure
- No segment shows promise

---

## 📊 TEST 5: SEARCH ENGINE

### Setup
- **Control:** A_hybris_search (9,500 users)
- **Treatment:** B_algolia_search (9,500 users)
- **Duration:** June 11-17, 2021 (7 days)
- **Primary Metrics:** avg_revenue_per_visitor, added_to_cart

---

### 🔍 METRIC ANALYSIS

#### 1. **Add to Cart Rate** ⭐⭐
```
Control (A):    89.9%
Treatment (B):  91.2%
Difference:     +1.4 percentage points (+1.51%)

95% CI:         [+0.53%, +2.19%]
99% CI:         [+0.36%, +2.36%]

Cohen's d:      0.046 (negligible effect size)
P-value:        0.001 ** (significant)
Power:          89% ✅

Interpretation: Algolia IMPROVES conversion significantly
```

**Apa artinya?**
- Algolia search engine meningkatkan cart additions 1.4 percentage points
- Effect size kecil TAPI statistically robust
- Power 89% (close to ideal 80%+)
- CI tidak cross zero → effect REAL

**Business Impact:**
```
Per 1,000 visitors:
- Hybris:  899 add to cart
- Algolia: 912 add to cart
- GAIN:    +13 conversions (+1.4%)

Annual impact (assuming 1M users/month):
+168,000 cart additions/year
```

---

#### 2. **Average Revenue per Visitor**
```
Control (A):    $0.867
Treatment (B):  $0.878
Difference:     +$0.011 (+1.26%)

95% CI:         [-$0.009, +$0.031]
99% CI:         [-$0.014, +$0.036]

Cohen's d:      0.015 (negligible)
P-value:        0.289 (NOT significant)
Power:          19% ❌

Interpretation: NO significant revenue impact
```

**Apa artinya?**
- Revenue effect TIDAK signifikan
- CI crosses zero → uncertain direction
- Butuh 66,248 users per grup untuk 80% power
- Test too short (7 days) untuk revenue metric

---

### 📱 SEGMENTATION ANALYSIS

**For add_to_cart metric:**

All segments show POSITIVE trend but NOT significant:
```
Device:   All positive, none significant
Browser:  Edge +3.41%, Safari +2.59% (not sig)
Region:   Split +4.10% (closest to significant)
```

**Insight:** Effect consistent but modest across segments

---

### 🎯 CONVERSION FUNNEL

```
Hybris Search (A):   89.9% █████████████████▓▓
Algolia Search (B):  91.2% ██████████████████▓

Improvement: +1.3 percentage points
```

Small but meaningful improvement in conversion!

---

### 💡 FINAL RECOMMENDATION - TEST 5

```
╔══════════════════════════════════════════════════════╗
║  ✅ ACCEPT: SWITCH TO ALGOLIA SEARCH                  ║
║                                                      ║
║  Confidence Level: ⭐⭐⭐⭐ (High)                       ║
║  Cart Effect: +1.51% (p=0.001)                      ║
║  Power: 89% (Strong)                                ║
║  Business Value: Positive                           ║
╚══════════════════════════════════════════════════════╝
```

**Why proceed despite small effect?**
1. ✅ Statistically significant (p=0.001)
2. ✅ High power (89%)
3. ✅ Positive business impact
4. ✅ Likely additional benefits:
   - Better search relevance
   - Faster results
   - Better UX (qualitative)

**Action Items:**
1. ✅ Implement Algolia search
2. 📊 Continue monitoring for 3 months
3. 💰 Track revenue impact longer-term
4. 🔍 Measure qualitative improvements:
   - Search speed
   - Result relevance
   - User satisfaction

---

## 📚 STATISTICAL CONCEPTS EXPLAINED

### Cohen's d (Effect Size)

**Apa itu?**
Ukuran seberapa BESAR perbedaan antara dua grup, di-standardize.

**Formula:**
```
Cohen's d = (Mean_Treatment - Mean_Control) / Pooled_StdDev
```

**Interpretasi:**
- **|d| < 0.2:** Negligible (hampir tidak ada perbedaan)
- **0.2 ≤ |d| < 0.5:** Small (perbedaan kecil)
- **0.5 ≤ |d| < 0.8:** Medium (perbedaan sedang)
- **|d| ≥ 0.8:** Large (perbedaan besar)

**Contoh Real:**
```
Test 1 - Add to Cart:
- Control: 96.2%, Std: 19.2%
- Treatment: 86.2%, Std: 34.5%
- Pooled Std: 27.9%
- Cohen's d = (86.2 - 96.2) / 27.9 = -0.357 (Small)

Meskipun "small", dampak bisnis BESAR karena:
- Base rate tinggi (96%)
- Absolute drop 10% sangat significant
```

**Key Takeaway:** Small effect size ≠ Small business impact!

---

### Statistical Power

**Apa itu?**
Probabilitas kita akan detect effect JIKA effect memang ada.

**Formula (simplified):**
```
Power = P(Reject H0 | H1 is true)
      = 1 - β (beta error)
```

**Interpretasi:**
- **Power 80%:** Standard industri (good)
- **Power < 80%:** Underpowered (risky)
- **Power > 90%:** Excellent (very confident)

**Contoh:**
```
Test 1 - Revenue:
Power = 100%

Artinya: Jika ada effect (even tiny), kita PASTI detect.
Conclusion: Result sangat reliable!

Test 4 - Add to Cart:
Power = 22%

Artinya: Bahkan jika ada effect, kita hanya punya 22% chance detect.
Conclusion: Test underpowered, tapi effect memang kecil.
```

**Faktor yang mempengaruhi Power:**
1. Sample size ↑ → Power ↑
2. Effect size ↑ → Power ↑
3. Variance ↓ → Power ↑
4. Alpha ↑ → Power ↑

---

### Confidence Intervals

**Apa itu?**
Range di mana kita "confident" true effect berada.

**95% CI Interpretation:**
"Jika kita repeat experiment 100x, 95x true effect akan dalam range ini"

**Contoh:**
```
Test 1 - Revenue Impact: -10.51%
95% CI: [-13.7%, -7.3%]

Artinya:
- Best case: Revenue turun 7.3%
- Worst case: Revenue turun 13.7%
- Most likely: Revenue turun 10.5%

Kesimpulan: Bagaimanapun, revenue TURUN (bad news)
```

**99% CI vs 95% CI:**
```
95% CI: [-13.7%, -7.3%]  (narrower)
99% CI: [-14.5%, -6.5%]  (wider)

99% CI lebih "confident" tapi kurang precise.
```

---

## 🎓 KEY LESSONS LEARNED

### 1. **Effect Size ≠ Business Impact**
```
Small Cohen's d CAN have huge business impact
Example: Test 1
- Cohen's d = -0.15 (negligible)
- Business impact = -$4.4M/year (HUGE!)

Always consider BOTH statistical AND practical significance!
```

---

### 2. **Power Matters More Than P-value**
```
Low power + Not significant ≠ "No effect"
It means: "We don't know, sample too small"

Example: Test 4
- p = 0.233 (not sig)
- Power = 22% (very low)
- Conclusion: Effect might exist, but too small to matter
```

---

### 3. **Segmentation Reveals Hidden Insights**
```
Overall effect might mask important segments!

Example: Test 2
- Overall: +5.8%
- Tablets: +12.8% (WOW!)
- Osijek: 0% (interesting!)

Action: Target high-performing segments first
```

---

### 4. **Time Matters**
```
7 days for behavioral metrics: OK
7 days for revenue metrics: Too short!

Test 5: 
- Cart rate: Significant (7 days OK)
- Revenue: Not significant (need more time)
```

---

### 5. **Covariate Balance is Critical**
```
Imbalanced covariates = Biased results

Test 2 & 3: Critical imbalances
→ Results unreliable without adjustment
→ NEVER skip balance checks!
```

---

## 📊 SUMMARY TABLE

| Test | Primary Metric | Effect | P-value | Power | Decision |
|------|---------------|--------|---------|-------|----------|
| 1. Menu | Revenue | -10.5% | <0.001 | 100% | ❌ REJECT B |
| 2. Novelty | Revenue | +5.8% | <0.001 | 100% | ⚠️ ADJUST FIRST |
| 3. Sliders | Revenue | Varies | <0.001 | - | ⚠️ ANALYZE |
| 4. Reviews | Cart | +0.5% | 0.233 | 22% | ❌ NO VALUE |
| 5. Search | Cart | +1.5% | 0.001 | 89% | ✅ ACCEPT B |

---

## 🎯 FINAL RECOMMENDATIONS

### Immediate Actions ✅
1. **Test 1:** Keep horizontal menu
2. **Test 5:** Switch to Algolia search
3. **Test 4:** Abandon featured reviews

### Pending Actions ⏳
1. **Test 2:** Apply CUPED, re-analyze, then decide
2. **Test 3:** Conduct thorough covariate analysis

### Long-term Improvements 🚀
1. Always run power analysis BEFORE test
2. Monitor covariate balance DURING test
3. Use longer test duration for revenue metrics
4. Implement CUPED by default
5. Segment analysis for all tests

---

**Report Compiled By:** Statistical Analysis Team  
**Date:** February 6, 2026  
**Contact:** data-science@company.com
