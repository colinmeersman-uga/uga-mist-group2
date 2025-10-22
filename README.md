Data # Group 2 MIST 4610 Group Project 1

## Team Name
15058 Group 2 

## Team Members
- Colin Meersman cmm08294@uga.edu
- Aaron Silverman abs87438@uga.edu
- Sanjot Bodake ssb46835@uga.edu
- Divya	Kadiyala dk94810@uga.edu
- Laiba	Syed ls76725@uga.edu

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

1. List all rides available in the park, ordered by ride type

<img width="827" height="793" alt="Screenshot 2025-10-21 114746" src="https://github.com/user-attachments/assets/aaa2867f-ea57-4145-b429-a08e09ee03d9" />


2. List all products sold in the park's gift shops along with their category

<img width="334" height="517" alt="Screenshot 2025-10-21 115246" src="https://github.com/user-attachments/assets/cea4b8ec-721d-467b-ac1c-86ff2fec160e" />


3. Find all shows scheduled in the Sunset Dome area

<img width="570" height="547" alt="Screenshot 2025-10-21 200715" src="https://github.com/user-attachments/assets/c29a8214-31dd-4351-baeb-bc1504cf166e" />


4. Display the Type of Ticket sold and the amount of tickets for ticket types "VIP" and "Season Pass"

<img width="550" height="441" alt="image" src="https://github.com/user-attachments/assets/26ada2f9-fb4c-4bf3-83b0-a4c1215fce36" />


5. Which rides have been used the most by customers, and how often has each been used?

This query helps management identify which rides attract the most guests throughout the park. Knowing which attractions are most popular allows managers to allocate resources such as maintenance teams, cleaning staff, and ride operators more effectively. Highly trafficked rides may need more frequent safety checks or longer operating hours. Conversely, rides with fewer uses may need promotional strategies or redesigns to boost interest. By ranking rides based on total usage, managers can prioritize investments in attractions that contribute most to guest satisfaction and park revenue.

<img width="712" height="633" alt="image" src="https://github.com/user-attachments/assets/015fb5eb-3d7f-4161-bb8d-a2bbf7e3c856" />


6. Which customers have spent the most money on products in the park?

This query helps management identify high-value customers who contribute the most to merchandise and food sales within the park. These customers are prime candidates for loyalty programs, exclusive discounts, or early access to new attractions. From a marketing perspective, understanding who your top spenders are also provides insight into spending habits and preferences, allowing the park to tailor promotions or bundles that encourage repeat visits. In addition, managers can assess whether the most profitable customers are frequent visitors or one-time guests, which helps shape guest retention strategies.

<img width="821" height="605" alt="image" src="https://github.com/user-attachments/assets/58c0e8dd-3e73-40e4-9745-e275b18419af" />


7. Which games have the highest average customer score?

This query helps the park’s entertainment and arcade managers measure the guest enjoyment of different games. A higher average score may indicate games that are both engaging and well-designed. These insights help managers identify which games to feature more prominently or which to replicate in new areas of the park. Conversely, games with low average scores may need to be rebalanced, updated, or replaced. From a strategic standpoint, understanding what guests find rewarding enhances the park’s overall entertainment value and can drive repeat visitation to the arcade area.

<img width="620" height="599" alt="image" src="https://github.com/user-attachments/assets/0eb1e3b8-b745-4543-9521-3448316d2119" />


8. Which rides are most popular in the afternoon (12 PM–6 PM)?

 This query identifies which rides experience peak activity during the afternoon, a common time when guest traffic increases after lunch. This information helps managers optimize scheduling by ensuring that adequate staff are present at the most popular rides during these hours. It can also inform operational decisions such as maintenance timing, queue management, and promotional scheduling. Knowing afternoon demand patterns allows the park to reduce wait times, improve guest satisfaction, and boost operational efficiency during high-traffic hours.

<img width="748" height="658" alt="image" src="https://github.com/user-attachments/assets/0e31bfa0-842f-4fd0-9c73-4e8dc21e9963" />


9. Which departments are spending more than their allocated budget?

This query allows park administrators and finance teams to identify departments exceeding their spending limits. Monitoring departmental budgets helps ensure financial discipline and efficient use of resources. Overspending could indicate operational inefficiencies, supply chain issues, or mismanagement. Detecting such issues early allows the park to take corrective action, such as re-evaluating procurement processes or adjusting future budget allocations. This promotes accountability and ensures that overall park expenses remain within financial goals.

<img width="899" height="491" alt="image" src="https://github.com/user-attachments/assets/40dc2c04-7d79-42fc-a5e1-81a9a37c9049" />


10. Which shows have had the most customer attendance?

Entertainment managers can use this query to evaluate which live shows or performances attract the largest audiences. Popular shows may justify adding additional performance times, larger venues, or merchandise tie-ins. Conversely, shows with low attendance might need marketing adjustments or creative revamps. Understanding guest preferences allows the park to design entertainment that aligns with visitor expectations and boosts overall satisfaction.

<img width="863" height="623" alt="image" src="https://github.com/user-attachments/assets/c3b1b0fb-5ab3-4f8b-9fe4-89e533b6b1d6" />




## Database Information
