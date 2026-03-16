#  Locker Guard: Inactivity Alert System

##  Overview
I developed the **Locker Guard** system to bridge the gap between silent student data and proactive customer success. By monitoring locker activity in real-time, I built a system that identifies "at-risk" students (inactive for 3+ days) and triggers an automated check-in before they churn.

## The Technical Stack
* **Database:** Supabase (PostgreSQL)
* **Automation:** Make.com
* **Visualization:** Looker Studio
* **Communication:** Gmail API

---

## Technical Implementation

### Phase 1: Data Infrastructure (Supabase)
I configured a Supabase database to track student behavior, specifically monitoring the `last_opened` timestamp to calculate engagement.

![Figure 1](https://github.com/Paulinus26/Locker-Guard-Automation/blob/28b475a8e730a990d9f8a2d49dc3907666e134c3/figure%201.png?raw=true)
*Figure 1: The backend data view showing active records and activity timestamps.*

### Phase 2: Logic & Automation (Make.com)
The core logic utilizes a rolling 72-hour window. I used the `addDays` and `formatDate` functions to flag students the moment they hit the inactivity threshold.

![Figure 2](https://github.com/Paulinus26/Locker-Guard-Automation/blob/main/figure%202.png?raw=true)
*Figure 2: The logic engine filtering for students who haven't accessed their locker in 3+ days.*

### Phase 3: Visual Analytics (Looker Studio)
I built a "Pause Risk" dashboard to provide the team with a bird's-eye view of campus health.

![Figure 3](https://github.com/Paulinus26/Locker-Guard-Automation/blob/main/figure%203.png?raw=true)
*Figure 3: Risk Gauge and student list built using custom DATE_DIFF metrics.*

### Phase 4: Verification of Output (Gmail)
The final result is a context-rich alert delivered directly to the support team for immediate outreach.

![Figure 4]([images/image_e2bce4.png](https://github.com/Paulinus26/Locker-Guard-Automation/blob/28b475a8e730a990d9f8a2d49dc3907666e134c3/figure%204.png?raw=true))
*: The automated outreach email received in the inbox.*

---

##  Impact & Maintenance
* **Proactive Retention:** Identifying churn risk within 72 hours.
* **Operational Efficiency:** Zero manual log-checking.
* **Deployment:** The system is live, toggled **ON**, and scheduled to run daily at 8:41 PM.

![Figure 5: Active Deployment](images/image_1cecfb.png)
*Figure 5: Scenario status showing active scheduling and live deployment.*

##  Conclusion
Building this system moved our support team from **reactive** (waiting for problems) to **proactive** (preventing churn). It is an efficient, scalable safety net that ensures we help students stay engaged before they decide to unsubscribe.
