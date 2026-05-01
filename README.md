# Logistics Audit: Veridi "Last Mile" Performance Report

### A. The Executive Summary
An audit of Veridi Logistics' delivery data reveals that logistics delays are the primary driver of negative customer sentiment, with "Super Late" packages plummeting to an average rating of **1.73 stars** compared to **4.29 stars** for "On Time" deliveries. Geographically, these delays are not a nationwide problem but are concentrated in specific regions; remote states like **Alagoas (AL)** suffer a disproportionate **21.4% late delivery rate**. Furthermore, bulky items in the "Bed, Bath & Table" category are the most frequent culprits for delays, indicating a need to re-evaluate regional distribution strategies and large-freight carrier partnerships.

### B. Project Links
*   **Link to Dashboard:** [Google Looker Studio Report](https://datastudio.google.com/reporting/7291c244-2476-4668-9845-7230d7c3f181)
*   **Link to Notebook:** [Google Colab Analysis](https://colab.research.google.com/drive/1IgBbJ2-WU9sQkIBQYcKelAjOGJZW16Np?usp=sharing)
*   **Link to Presentation:** [Insight Slide Deck](https://docs.google.com/presentation/d/1A37jo2wHk7vTQV3Ddrq3lQjAed0Aq32z6stlg8W7eRo/edit?usp=sharing)

### C. Technical Explanation
*   **Data Cleaning:** During the initial table joins, I identified a 1-to-many relationship issue between the `orders` and `reviews` tables that artificially inflated the dataset (caused by customers leaving multiple reviews for a single order). I resolved this by applying a `.drop_duplicates(subset=['order_id'])` function immediately after the join to guarantee data integrity and ensure each order was only counted once in volume metrics.
*   **Candidate's Choice:** For my custom analysis, I evaluated the **Average Shipping Cost (`freight_value`)** against **Delivery Status**. I selected this metric because it highlights a critical customer churn risk: customers are actually paying a higher premium (an average of **23.85 Real**) for packages that end up arriving "Super Late," compared to lower shipping costs (**19.75 Real**) for on-time packages. This "premium price for poor service" model represents a major threat to customer loyalty.

---

## 🛑 Final Submission Checklist
- [x] GitHub Repo is Public.
- [x] .ipynb notebook file is uploaded.
- [x] HTML or PDF export of the notebook is uploaded.
- [x] Dashboard link is public (Tested in Incognito).
- [x] Presentation link is public (Tested in Incognito).
