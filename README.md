# StreamFlix – Streaming Platform Data Analysis

## 📌 Scenario
StreamFlix is a globally growing subscription-based video-on-demand (VOD) platform that provides entertainment services to users across different countries. 

The company wants to develop a comprehensive Streaming Management System to store and manage its daily viewing activities, user subscriptions, and content library in a structured database. The system will maintain information about users, profiles, subscription plans, content, and watch history.

### 1. Users
The platform stores personal and account information about every user, such as their email, country, registration date, and account status. A user is subscribed to a particular plan and can create one or more viewing profiles.

### 2. Profiles
Users can create different profiles under their main account to keep viewing preferences separate. The system stores the profile name and the designated age group (Kids, Teen, Adult). Each profile is linked to a specific user.

### 3. Plans
StreamFlix offers different subscription tiers to its users, such as:
- Basic
- Standard / Regular
- Premium

Each plan is linked to a user account. The system stores the plan name, monthly price, and maximum streaming resolution (e.g., 4K). 

### 4. Content
The platform hosts a massive library of entertainment. The system stores different types of content, such as:
- Movies
- TV Shows

For every piece of content, StreamFlix stores the title, genre, release year, duration in minutes, and maturity rating.

### 5. Watch History
Users perform streaming activities through their profiles. The system records all viewing sessions, including:
- The date the content was watched
- The total minutes watched

One profile can have many watch history records, and one piece of content can be streamed multiple times.

---

## 📊 StreamFlix SQL Project – Business Analysis Questions

### A. User & Basic Analysis
1. StreamFlix wants to maintain a user directory. Display complete details of all registered users.
2. Management wants to know the different countries StreamFlix users are coming from. Display the unique user countries.
3. Identify all users whose current account status is 'Active'.
4. Find users who are registered in either the 'Premium' or 'Standard' plan (PlanID 2 or 3).
5. Identify users who are registered in countries other than the 'United Kingdom'.
6. Find users who registered between January 1, 2023, and December 31, 2023, for cohort analysis.
7. Identify users belonging to 'Canada', 'Australia', 'Germany', or 'France'.
8. Find users whose email addresses begin with the letter 'M'.
9. Identify users whose billing country is missing in the database records.
10. Identify users who have a registered email address on file.
11. Display user accounts ordered from oldest registration date to newest to identify long-term loyal customers.
12. Identify the top 5 most recently registered users to track daily acquisition.
13. Find 'Active' users who are currently registered in the 'United States' or 'India'.
14. Generate a formatted display label for customer service agents that combines the user's Email and their Country.
15. Ensure all user emails are standardized in entirely lowercase letters for the data warehouse migration.
16. Extract just the first 4 characters of the User's Email to create a short, temporary username.
17. The data team is generating a daily report of all active users. Add a column called `ReportGeneratedDate` that stamps every row with today's exact date.
18. The finance team wants to analyze yearly growth. Extract just the year from the `RegistrationDate` to see what year each user joined.
19. Marketing wants to see if there is a seasonal spike in signups (like around the holidays). Extract the month name from every user's registration date.
20. Customer success wants to calculate the "Account Age" for every user. Find the number of days between the user's `RegistrationDate` and today.

### B. Profile & Demographic Segmentation
1. Identify profiles that belong to the 'Kids' age group.
2. Find profiles whose profile names contain the word 'Guest'.
3. Display profiles belonging to users from 'India' that are grouped under the 'Adult' age category.
4. Identify profiles whose age group is neither 'Kids' nor 'Teen'.
5. Display profiles whose name starts with the letter 'S'.
6. Find users whose email addresses belong to the Gmail domain.
7. Sometimes users accidentally type an extra space before or after their profile name. Clean the profile names by removing leading/trailing spaces.

### C. Content Library Monitoring
1. Display all content with their type, title, genre, and duration.
2. Identify movies (`ContentType = 'Movie'`) that have a duration strictly greater than 120 minutes.
3. Find content with a duration between 30 and 90 minutes.
4. Identify content that belongs to the 'Documentary' or 'Educational' genre.
5. Display the single movie with the shortest duration in the catalog.
6. Calculate the total number of content titles available on the platform.
7. Calculate the average duration of all movies in the 'Action' genre.
8. The marketing team wants a list of all movie titles displayed in ALL CAPS for a new promotional flyer.
9. Find the length (number of characters) of each content title to identify long titles that might get cut off on the mobile app UI.

### D. Subscription Plan & Revenue Analysis
1. Display all subscription plans along with their price and max resolution details.
2. Identify plans that offer '4K' resolution.
3. Find the number of users subscribed to each plan type.
4. Calculate the total potential monthly revenue generated by all 'Active' users per plan.
5. Identify plans that have more than 10 active subscribers in this dataset.
6. Find the `PlanName` with the highest number of registered users.
7. The platform is rebranding the "Standard" plan to be called "Regular". Display the plans, replacing the word "Standard" with "Regular".

### E. Viewing Activity & Engagement Analysis
1. Display all watch history along with profile names and watch dates.
2. Identify profiles that have watched a 'TV Show' in the last 30 days.
3. Find profiles that have watched both 'Movies' and 'TV Shows'.
4. Identify specific watch sessions where the `MinutesWatched` is greater than 150 minutes.
5. Calculate the total watch time (in minutes) for each content genre.
6. Find the average watch time per session for each specific `AgeGroup`.
7. Identify the profile with the highest total `MinutesWatched` across all time.
8. The content team wants to know if people watch more shows on weekends. Extract the name of the day from the watch date.

### F. Content Performance Analysis
1. Display all 'Sci-Fi' movies along with their release years and ratings.
2. Identify content titles that have been watched for a total of more than 300 minutes platform-wide.
3. Calculate the average completion percentage for documentaries.
4. Calculate the total watch time for each specific `ContentType` (Movie vs. TV Show).
5. Identify the specific Content Title with the highest overall watch time.
6. **Identifying "Dead" Content:** Display a list of all Content Titles and their total minutes watched, including content that has never been watched.

### G. User Viewing Behavior
1. Identify users whose total minutes watched is greater than the platform average.
2. Identify users who have an 'Active' subscription status but 0 records in the `WatchHistory` table.
3. Identify users who have created multiple profiles (more than 3).
4. Find profiles who have both a 'Kids' `AgeGroup` and have watched 'R-rated' content.

### H. User & Platform Relationship Analysis
1. Display each profile's name along with the subscription plan name their parent account is paying for.
2. Generate a consolidated dashboard view showing User Email, Profile Name, Plan Name, Content Title, and Minutes Watched for every viewing session.
3. Identify profiles operating under the same User Account (list `UserID` and the count of all associated profiles).

### I. Advanced & Cross-Content Preference Analysis
1. Identify profiles that are watching both 'Action' movies and 'Comedy' movies.
2. Identify profiles that have watched 'TV Shows' but have never watched a 'Movie'.
3. Identify users who have a 'Premium' plan but only have 1 profile created (Underutilizing their plan).
4. Rank the most popular content (by total `MinutesWatched`) within each specific genre.
5. **Cross-Genre Audience Overlap:** Find the profiles of users who have watched at least one 'Sci-Fi' title and overlap that with profiles who have watched 'Documentaries'.

### J. Customer & Content Risk Classification
1. **CASE** – Classify profiles into 'Children', 'Teenagers', and 'Adults' based on their `AgeGroup`.
2. **CASE** – Classify content duration into 'Short' (<40 mins), 'Standard' (40-120 mins), and 'Epic' (>120 mins).
3. **CASE** – Classify watch sessions into 'Bounce' (<15 mins), 'Casual' (15-60 mins), and 'Binge' (>60 mins) based on minutes watched.
4. **CASE** – Classify User accounts based on their status as 'No Risk', 'At Risk', or 'Churned'.
5. **SUBQUERY** – Find the Profile Names of all profiles whose parent user account is 'Cancelled'.
6. **IF** – Create a report showing user emails and a new column classifying them as 'Domestic' or 'International' based on their country.

---

## 💡 PROJECT CONCLUSION
The StreamFlix SQL analysis provides a complete view of the platform's users, profiles, subscription plans, content catalog, and watch history.

The analysis helps StreamFlix understand user demographics, monitor account revenue, evaluate content performance, track streaming engagement, and analyze viewing habits. 

User and platform behavior analysis helps the company identify high-value subscribers, active streaming relationships, multiple-profile accounts, and users interacting with different genres and content types. `CASE`-based classification further helps StreamFlix segment audiences, viewing durations, and user retention risks for better analysis.

Overall, this SQL project demonstrates how streaming and VOD data can be organized, analyzed, and transformed into meaningful business insights for better decision-making.

```
