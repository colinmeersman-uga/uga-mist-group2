Data # Group 2 MIST 4610 Group Project 1

## Team Name
F25MIST4610_15058_Group2

## Team Members
- Colin Meersman cmm08294@uga.edu - https://github.com/colinmeersman-uga/uga-mist-group2
- Aaron Silverman abs87438@uga.edu - https://github.com/abs87438/uga-mist-group2
- Sanjot Bodake ssb46835@uga.edu - https://github.com/sbodake1/MIST4610Project
- Divya	Kadiyala dk94810@uga.edu - https://github.com/dk94810-lang/MIST-4610-
- Laiba	Syed ls76725@uga.edu - https://github.com/ls76725/uga-mist-group2

## Scenario Description
A local amusement park, UGA Amusement, has asked you to design a database to manage information about its daily operations, attractions, and visitors. 

Guests who visit the park are represented as customers. For each customer, the park records a unique ID, name (first and last), email, and phone number. Customers can purchase different types of tickets (for entry) and fast passes (for skipping lines). A customer can hold many tickets or fast passes, but each ticket or pass belongs to only one customer.

Customers can attend games, shows, and ride attractions during their visit. The GamePlay tracks the score earned during the duration of each game played by a customer. The ShowAttendance tracks which customer attended which show on what date. While the RideUsage notes which rides were taken by which customer and when.

The park also has a variety of products for sale at the Gift Shop, which has its own ID, name, location, and open hours. Each product has an ID, name, category, and price. Products are linked to purchases made by customers. The Purchase stores info about the purchase ID, date, total amount, and payment method. While the purchaseProduct tracks each product purchased, along with the quantity of products included in each purchase.

UGA Amusement employs a large number of employees to manage park operations. For each employee, the database stores ID, name, role, hire date, and salary. Each employee works in one department. The departments include an ID, name, location, budget, and phone number.

## Data Model
Explanation of Data Model

Our model represents the structure of UGA Amusement and its various operations, attractions, and customer interactions.

At the center of this model is the Customer entity, which stores details such as each customer’s name, email, and phone number. Customers are involved in nearly every area of the park’s system — buying tickets, attending shows, playing games, and making purchases — so this entity serves as a hub for multiple relationships.

Each Customer can buy multiple Tickets, represented by the one-to-many relationship between the Customer and Ticket tables. The Ticket table records the ticket type, purchase date, and price. Some guests also receive Fast Passes, which allow priority access to certain rides. Because each Fast Pass corresponds to a single ticket, we have a one-to-one relationship between Ticket and Fast Pass.

Customers can also purchase products from the park’s various Gift Shops. Purchases include the purchase date, total amount, and payment method. Since a purchase can contain multiple products and each product can appear in multiple purchases, we use an associative entity called PurchaseProduct between Purchase and Product. This table includes details such as quantity to show what was bought and in what amount. The Product table itself stores product names, prices, and categories, while the Gift Shop table represents each shop’s name, location, and operating hours. A one-to-many relationship exists between Gift Shop and Product since each shop sells multiple items.

The Department and Employee entities represent the park’s internal organizational structure. Each employee works within a specific department (such as Security, Maintenance, or Guest Services), so there is a one-to-many relationship between Department and Employee. Employees are also linked to the rides and gift shops they manage and operate, connecting the operational side of the park to its attractions and retail spaces.

Attractions are represented by several entities. The Ride entity contains information about each ride’s name, type, and minimum height requirement. Customers can use rides, creating a one-to-many relationship between Ride and RideUsage, which records when a customer used a particular ride.

Entertainment within the park is captured through the Show entity, which includes each show’s name, showtime, and location. Customers attending shows are tracked through the ShowAttendance table — an associative entity that shows which customer attended which show and when.

The Game and Gameplay entities represent the park’s arcade and game activities. Each game has attributes like name, type, and location, while Gameplay tracks which customer played which game and the score they achieved. This relationship is many-to-many, implemented through the Gameplay table.

Altogether, this data model illustrates how guests interact with various aspects of the theme park — from rides, shows, and games to purchases and ticketing — while also representing how departments, employees, and retail operations support the park’s daily functions.

<img width="1385" height="729" alt="Screenshot 2025-10-21 113656" src="https://github.com/user-attachments/assets/d952648c-edc1-4bdd-98bc-bc1578cbd019" />

## Data Dictionary
![Customer Table](CustomerTable.png)
<img width="1304" height="648" alt="image" src="https://github.com/user-attachments/assets/ed4622f0-5e75-4c40-9d65-71dd1aa3ae86" />
<img width="1300" height="570" alt="image" src="https://github.com/user-attachments/assets/98f05a03-a9a1-4d10-ad82-32f8de6e91a7" />
<img width="1164" height="500" alt="image" src="https://github.com/user-attachments/assets/7f915962-bd57-4523-9c77-3ba765946d47" />
<img width="1180" height="546" alt="image" src="https://github.com/user-attachments/assets/496dac0b-d5ab-44e4-9f16-22e667d10b16" />
<img width="1428" height="538" alt="image" src="https://github.com/user-attachments/assets/0e4d5d87-e72c-450e-9018-e3f3e3053a03" />
<img width="606" height="164" alt="image" src="https://github.com/user-attachments/assets/689601e1-2cb4-412b-b590-437f222e21d8" />
<img width="1214" height="464" alt="image" src="https://github.com/user-attachments/assets/481d9862-1496-45fa-bdf9-22932ee44f39" />
<img width="1434" height="576" alt="image" src="https://github.com/user-attachments/assets/fd633ca5-adb9-42b2-bdfa-8afacc5a9e0d" />
<img width="692" height="292" alt="image" src="https://github.com/user-attachments/assets/1403d935-13cf-435b-9152-a17c88a259f9" />
<img width="1300" height="460" alt="image" src="https://github.com/user-attachments/assets/8a5ed138-2b20-4ccf-a85b-7f0bf81bcb11" />
<img width="1238" height="398" alt="image" src="https://github.com/user-attachments/assets/b2f6b57c-867f-434b-83cf-70f0f66f8428" />
<img width="1208" height="532" alt="image" src="https://github.com/user-attachments/assets/b6756d82-e396-4ba9-99a4-37942dd49f83" />
<img width="1256" height="634" alt="image" src="https://github.com/user-attachments/assets/52c79d80-f170-49d3-9f76-97998a83e392" />
<img width="1264" height="604" alt="image" src="https://github.com/user-attachments/assets/0aba1dcf-67ec-4df2-a461-225a33401f77" />



## Queries

Q1. List all rides that have 'Coaster' or 'Mountain' in their name

This query helps park management quickly identify all thrill-oriented attractions, such as roller coasters or mountain-themed rides. Knowing which rides fit into this category is useful for marketing campaigns and promoting adrenaline attractions to target audiences.

<img width="533" height="525" alt="image" src="https://github.com/user-attachments/assets/f095058f-1611-4040-bd12-e4bdb44cfe46" />


Q2. Find all shows scheduled in the Sunset Dome area at 4 pm

Knowing how to find all shows scheduled in the Sunset Dome area at 4 p.m. is important because it allows event organizers, staff, and visitors to efficiently plan and manage their time. For staff, it ensures proper coordination of resources such as security, maintenance, and crowd control. For guests, it helps them make the most of their visit by easily locating entertainment options that fit their schedule. Overall, this information supports smooth event operations and enhances the overall visitor experience.

<img width="720" height="314" alt="image" src="https://github.com/user-attachments/assets/92714de6-2967-4c50-8437-ac61d3995a4c" />


Q3. Shows all customers that haven’t been on a ride

This query identifies guests who aren’t engaging with rides and sends them tailored offers like ride coupons, express access, or beginner-friendly recommendations. It also enables the park to spot patterns (e.g., families, older visitors) to adjust signage, accessibility, or ride mix to better serve under-engaged segments.

<img width="1171" height="386" alt="image" src="https://github.com/user-attachments/assets/b2cc82df-299a-41e9-bbf8-3c174185a430" />


Q4. Which rides have been used the most by customers, and how often has each been used?

This query helps management identify which rides attract the most guests throughout the park. Knowing which attractions are most popular allows managers to allocate resources such as maintenance teams, cleaning staff, and ride operators more effectively. Highly trafficked rides may need more frequent safety checks or longer operating hours. Conversely, rides with fewer uses may need promotional strategies or redesigns to boost interest. By ranking rides based on total usage, managers can prioritize investments in attractions that contribute most to guest satisfaction and park revenue.

<img width="803" height="655" alt="image" src="https://github.com/user-attachments/assets/2ced2093-e202-4e11-b59d-faf82963a745" />


Q5. Which customers have spent the most money on products in the park?

This query helps management identify high-value customers who contribute the most to merchandise and food sales within the park. These customers are prime candidates for loyalty programs, exclusive discounts, or early access to new attractions. From a marketing perspective, understanding who your top spenders are also provides insight into spending habits and preferences, allowing the park to tailor promotions or bundles that encourage repeat visits. In addition, managers can assess whether the most profitable customers are frequent visitors or one-time guests, which helps shape guest retention strategies.

<img width="821" height="605" alt="image" src="https://github.com/user-attachments/assets/58c0e8dd-3e73-40e4-9745-e275b18419af" />


Q6. Show each game’s total number of players, average score, highest score, and the top-performing player’s name

Analyzing game performance and player data is important because it helps park management understand which games are most engaging and profitable. By identifying the most popular games, average scores, and top players, managers can make data-driven decisions about where to allocate resources, schedule maintenance, or introduce new attractions. It also provides insights into customer preferences and participation trends, allowing the park to improve the overall guest experience and increase repeat visits.

<img width="1872" height="714" alt="image" src="https://github.com/user-attachments/assets/91eb74b0-7a99-4686-ae53-4313c8a3f068" />



Q7. Which rides are most popular in the afternoon (12 PM–6 PM)?

This query identifies which rides experience peak activity during the afternoon, a common time when guest traffic increases after lunch. This information helps managers optimize scheduling by ensuring that adequate staff are present at the most popular rides during these hours. It can also inform operational decisions such as maintenance timing, queue management, and promotional scheduling. Knowing afternoon demand patterns allows the park to reduce wait times, improve guest satisfaction, and boost operational efficiency during high-traffic hours.

<img width="748" height="658" alt="image" src="https://github.com/user-attachments/assets/0e31bfa0-842f-4fd0-9c73-4e8dc21e9963" />


Q8. Which departments are spending more than their allocated budget?

This query allows park administrators and finance teams to identify departments exceeding their spending limits. Monitoring departmental budgets helps ensure financial discipline and efficient use of resources. Overspending could indicate operational inefficiencies, supply chain issues, or mismanagement. Detecting such issues early allows the park to take corrective action, such as re-evaluating procurement processes or adjusting future budget allocations. This promotes accountability and ensures that overall park expenses remain within financial goals.

<img width="899" height="491" alt="image" src="https://github.com/user-attachments/assets/40dc2c04-7d79-42fc-a5e1-81a9a37c9049" />


Q9. Which shows have had the most customer attendance?

Entertainment managers can use this query to evaluate which live shows or performances attract the largest audiences. Popular shows may justify adding additional performance times, larger venues, or merchandise tie-ins. Conversely, shows with low attendance might need marketing adjustments or creative revamps. Understanding guest preferences allows the park to design entertainment that aligns with visitor expectations and boosts overall satisfaction.

<img width="863" height="623" alt="image" src="https://github.com/user-attachments/assets/c3b1b0fb-5ab3-4f8b-9fe4-89e533b6b1d6" />

Q10. Which gift shops have total sales greater than the park's average shop sales?

This query can help managers identify which shops are doing the best, or where to provide more resources, like inventory, or allocate more cash for the shop’s budget. This query can also help managers understand why some shops are not doing as well as other shops in the park to provide changes that will help improve them or even remove them.

<img width="1278" height="613" alt="image" src="https://github.com/user-attachments/assets/d628142d-e326-4a73-94fa-ca1dcb339352" />


<img width="1563" height="873" alt="image" src="https://github.com/user-attachments/assets/c6af64ee-d22d-409d-b74d-5ef9db8e2e21" />


## Database Information

Schema Name: ns_F25MIST4610_15058_Group2

Group Name: F25MIST4610_15058_Group2


Additional Notes: All Procedures have been stored within the database in the format"TP_Q1, TP_Q2, etc."

<img width="254" height="311" alt="image" src="https://github.com/user-attachments/assets/091dc394-8a5a-46c2-be73-2341286ada0d" />


