# Netflix | EDA & Business Insights

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?style=flat)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat)

---

## Business Problem

Netflix has over 10,000 titles and 222M+ subscribers globally (as of mid-2021). The goal of this analysis is to help Netflix's content team answer: **what type of content to produce, and in which markets, to maximise growth.**

---

## Dataset Overview

10,000+ titles with fields covering: `type`, `title`, `director`, `cast`, `country`, `date_added`, `release_year`, `rating`, `duration`, `listed_in` (genre), `description`

---

## Approach

### 1. Data Cleaning
- **Director** column had 29.9% missing values - filled with `"Unknown"` (dropping would bias analysis)
- **Cast** and **Country** similarly filled with `"Unknown"` for preservation
- **Country column exploded**: comma-separated multi-country entries (e.g. "Canada, Japan") were split and exploded using Pandas `str.split()` + `explode()` to enable accurate country-level analysis
- Date columns converted to `datetime` for month-level extraction

### 2. Univariate Analysis
- **Content split**: ~70% Movies, ~30% TV Shows on the platform
- **Top rating**: TV-MA dominates - Netflix is heavily adult-content focused; family/children's content is underrepresented
- **Top genres**: International Movies, Dramas, and Comedies lead; Documentaries and Stand-Up Comedy are growing segments (low production cost, high engagement)

### 3. Bivariate & Time-Series Analysis
- **Country-level content distribution**: US leads (2,364 titles), India second (927) - significant opportunity in emerging markets
- **Movie release trend**: peaked in 2017–2018, sharp decline post-2019 (COVID impact)
- **TV Show trend**: steady growth since 2015 with a more gradual post-2019 decline than movies
- **Inverse pattern**: years with high movie releases tend to have lower TV show additions, suggesting intentional content portfolio balancing

### 4. Optimal Launch Timing
- **Best month to launch a TV Show**: December (highest additions historically)
- **Strategic window**: February and May have the fewest new additions - launching in these months means less competition for viewer attention

---

##  Key Business Recommendations

1. **Invest in Indian and UK original content**  -both markets show strong consumption but are underrepresented in original productions
2. **Expand family and children's content** - current ratings distribution reveals a clear gap; capturing this segment diversifies the subscriber base
3. **Double down on Documentaries and Stand-Up Comedy** - high audience interest, lower production budgets, strong ROI potential
4. **Schedule marquee TV Show launches in December** - historically the highest-traffic month for new additions
5. **Use February and May as counter-programming windows** - fewer competitor releases = higher visibility for new launches

---

