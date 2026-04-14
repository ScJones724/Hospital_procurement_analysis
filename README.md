
# Clinical Stocktake & Procurement Analysis

## *From Data Chaos to Actionable Insights for a Local Hospital*

[](https://www.python.org/)
[](https://pandas.pydata.org/)
[](https://www.google.com/search?q=)
[](https://www.google.com/search?q=)

-----

## The Story Behind This Project

**The Problem:** A busy local hospital was flying blind. Stockouts weren't just a "logistics issue"—they were a daily stressor for clinical staff. The procurement team was working with two messy Excel files that simply didn't talk to each other. One used "pkts of 100," the other used "pairs," and some used "dozens." Nobody knew exactly when the last cannula would be used.

**The Question:** *"What do we need to order right now to keep this hospital running?"*

**The Answer:** This project. I built a Python-powered data pipeline that cleans the noise, standardizes the units, and calculates **Months of Supply (MOS)**. It turns "messy spreadsheets" into a clear, prioritized list of what to buy today, this week, and next month.

-----

## What This Project Does

| Problem | Our Solution |
| :--- | :--- |
| **Messy Data** (Merged cells, random `NaN` values, inconsistent headers) | **Auto-cleaning pipeline** that resets headers and drops the "garbage" rows automatically. |
| **Unit Mismatch** (Comparing "packets" to "pieces") | **Smart conversion logic** that brings everything down to a "Base Unit" so we compare apples to apples. |
| **Inventory Blindness** (No idea when stock runs out) | **MOS Calculation:** `Stock ÷ Monthly Usage` = A real-time countdown of months left. |
| **Surprise Stockouts** | **Traffic Light Alerts:** Flags items needing an order **TODAY** vs. **THIS WEEK**. |
| **Frozen Capital** | **Dead Stock ID:** Identifies items taking up space (and money) that haven't moved in months. |

-----

## The Impact: What We Found

After analyzing **162 inventory items**, the data told a clear story:

> ### **Emergency Status**
>
>   * **21 Items at ZERO Stock:** These are actively used items (Gloves, Syringes). **Order TODAY.**
>   * **6 Items at Critical Low:** Less than 1 month left. **Order THIS WEEK.**
>   * **131 Items Missing Data:** These items need our clinical team to provide usage estimates.
>   * **10 Items Confirmed Dead:** Discontinued brands that are just "frozen money" on the shelf.

**The Bottom Line:** Our analysis caught a looming crisis. The hospital was days away from running out of latex gloves, surgical gloves, syringes, and sutures.

-----

## Repository Structure

```text
clinical-stocktake-procurement/
│
├── 📂 data/             
├── 📂 notebooks/        
├── 📂 outputs/          
│   ├── ORDER_TODAY.csv
│   ├── ORDER_THIS_WEEK.csv
│   └── DEAD_STOCK_WRITEOFF.csv
├── 📂 docs/            
└── README.md           
```

-----

## 💀 Confirmed Dead Stock (Write-Off Recommended)

These items represent frozen capital. They are discontinued brands with zero movement. We recommend writing these off to clear shelf space.

  * *Synthecon, Polypropylene, Surgicril, Advacryl, Dermatech, Dermacryl (Various sizes).*

-----

## How to Use This (For Other Facilities)

1.  **Clone the Repo:** `git clone https://github.com/ScJones724/hospital-procurement-analysis.git`
2.  **Install Dependencies:** `pip install -r requirements.txt`
3.  **Add Your Data:** Drop your messy Excel files into the `/data` folder.
4.  **Run the Analysis:** Open `notebooks/clinical_stock_analysis.ipynb` and run all cells.
5.  **Get Results:** Check the `/outputs` folder for your prioritized shopping list.

-----

## Key Lessons Learned

1.  **Unit Conversion is Vital:** You cannot calculate supply if you are mixing "packets" with "pairs." Normalizing to base units is the only way to get the truth.
2.  **Actionable \> Fancy:** Procurement officers don't need complex 3D charts; they need a CSV that tells them what to buy before the next shift starts.
3.  **Data is a Dialogue:** 81% of our items lacked consumption data. Instead of ignoring them, we created a **Clinical Review Template** to start a conversation with the theatre and ward leads.

-----

**Built with 🐍 Python and ☕ Coffee | April 2026**
*"In God we trust. All others must bring data."* — W. Edwards Deming

