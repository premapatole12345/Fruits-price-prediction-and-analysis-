# Fruits-price-prediction-and-analysis-
FruitCast --- Fruit Price Prediction & Analysis
FruitCast is a responsive, browser-based dashboard for exploring fruit-price patterns, comparing average prices, and generating indicative monthly price estimates.
Demo notice: The built-in dataset is illustrative. Estimates use a simple seasonal adjustment---not a trained production machine-learning model---and do not represent live market prices.
Features
Dashboard summary: Displays the number of fruits tracked, average price, highest price, and number of records.
Price prediction: Select a fruit and target month, enter a previous price, and calculate an indicative estimate.
Monthly trend chart: Visualizes average monthly prices for the available fruits.
Average price comparison: Compares average prices across fruits.
Fruit price overview: Shows each fruit's average price, latest price, and percentage change.
CSV upload: Load your own dataset using the required column names.
Reset demo: Restore the built-in sample dataset.
Responsive layout: Adapts to desktop and mobile screen sizes.
Built With
HTML
CSS
Vanilla JavaScript
HTML Canvas API for the monthly trend chart
No build step or external JavaScript library is required.
Run Locally
Download or clone this project.
Open index.html in a modern web browser.
You can also serve the folder with a local development server if preferred. The app runs in the browser and does not require a backend.
Using the Dashboard
Estimate a fruit price
Choose a fruit.
Select the target month.
Enter the previous price in rupees per kilogram.
Click Estimate price.
The dashboard calculates a seasonal adjustment from the loaded dataset and applies it to the entered previous price.
Upload a CSV dataset
Select a CSV file using the Upload your dataset control. The file must contain these columns:
Column             Description
Fruit            Fruit name Year             Year of the record Month            Month number, from 1 to 12 Previous_Price   Previous price; must be greater than zero Price            Recorded price; must be greater than zero
Example:
Fruit,Year,Month,Previous_Price,Price
Apple,2025,1,138.50,140.00
Banana,2025,1,44.00,45.00
Mango,2025,5,75.00,110.00
The app requires at least three valid data rows. Rows with missing fruit names, invalid numeric values, months outside 1--12, or non-positive prices are ignored.
CSV parsing note: The current parser splits rows on commas and is intended for simple CSV files. It does not support commas embedded inside quoted fields.
Prediction Method
For the selected fruit and month, the app calculates:
The average price for that fruit in the selected month across the loaded data.
The overall average price for that fruit across the loaded data.
A seasonal ratio: selected-month average / overall average.
An estimate using the entered previous price:
estimated price = previous price × (0.65 + 0.35 × seasonal ratio)
The result is prevented from falling below 0.01.
This is a lightweight illustrative formula. It should not be treated as a validated forecasting model or used as the sole basis for buying or selling decisions.
Built-in Demo Data
The initial dashboard generates sample monthly records for:
Apple
Banana
Mango
Orange
Grapes
The sample data covers 2022--2025 and uses predefined base prices, seasonal adjustments, and deterministic variation. These values are for demonstration only.
Project Structure
.
└── index.html   # Complete application: markup, styles, and JavaScript
Limitations
No backend, database, authentication, or external market-data connection is included.
The built-in data is synthetic/illustrative, not verified market data.
Predictions use a simple seasonal formula, not a trained ML model.
CSV parsing supports a basic comma-separated format only.
Prices are displayed in Indian rupees (₹) per kilogram.
Customization
Update the base object to change the demo base prices.
Update the seasonal object to change the monthly seasonal adjustments.
Update the fruitEmoji object to add or change fruit icons.
Replace the demo data generator with verified historical market records for more meaningful analysis.
License
No license information is specified in the source project. Add a LICENSE file if you intend to distribute the project.
