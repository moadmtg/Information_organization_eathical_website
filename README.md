# Eathical

Eathical is a platform that allows users to explore nutritional content, environmental footprints and optimized dietary choices.
It uses data from two databases, the Dutch Food Composition Database (NEVO) and the Life Cycle Analysis (LCA) Food Database. This data is combined to provide a comprehensive view the nutritional and environmental impact values different food products have.

---

## The Project

As stated above, Eathical informs users about nutritional values and environmental impact of certain foods. It does this by visualizing and comparing foods on multiple dimensions, such as:

- Nutritional content (e.g., protein, fiber, fat, vitamins, minerals)
- Environmental impact (e.g., CO₂ emissions, water consumption, land use)

Because of this overview, the website can be useful for users such as avid personal health trackers, dietitians, or teachers and researchers.

---

## Dataset

Two official Dutch databases are merged to form one dataset. These two databases are::

1. **NEVO – Dutch Food Composition Database (RIVM)**  
   This database contains data on the composition of foods, including energy and nutrients such as protein, fat and fatty acids, carbohydrates, vitamins and generals.

2. **2019 LCA Food Database (RIVM)**  
   Contains life cycle assessment data, leading to insights on the environmental impact of food products through variables such as CO2 emissions, land use, and water consumptions. The more recent, 2023 database version, was not used due to new data not having been subjected to critical review according to ISO 14040 standards, meaning figures could not be used to compare individual food products such as apples and pears. The 2019 database does allow for these types of comparisons.

Using the unique NEVO code a food product has, these databases were merged. This led to the final dataset that was used for the website, containing food products and their nutritional and environmental attributes. A note to add is that the LCA data was converted to a 100g basis for consistency.

---
## Running Eathical Online
1. **Open the following link to end up on the homepage of Eathical**
https://moadmtg.github.io/Information_organization_eathical_website/index.html

## Running Eathical Locally

### Steps:
1. **Download or clone the repository:**
   ```
   git clone https://github.com/moadmtg/Information_organization_eathical_website.git
   cd Information_organization_eathical_website

2. **Start a local server**
# Windows
py -m http.server 5500

# macOS/Linux
python3 -m http.server 5500

3. **Open the homepage:**
   - Go to your browser
   - Open http://localhost:5500/
   
---

## Website Structure and Tools

All webpages and tools are available through a global navigation bar located at the top of every page on the website. The website is fully responsive for both desktop and mobile devices.

### 1. Homepage (`index.html`)
The homepage introduces users to Eathical.  
It includes:
- A short intro video.
- Clickable cards linking to each major tool, showcasing all tools the Eathical website provides.

### 2. Food Matrix (`food_explorer_dashboard.html`)
Tool users can use to view compare nutritional and environmental values within a specific food group.  
Users can:
- Select a preferred food group.
- Search for a preferred food product within this group.
- Add/Remove columns to only obtain results in line with a users nutritional and environmental value wants or needs.
- Sort the filtered results by the chosen nutritional/environmental columns.

### 3. Food Comparison (`comparison_dashboard_final_v3Clean.html`)
Compares two foods (per 100 grams) selected by a user in a radar chart.
- A radar chart shows the nutritional and envrionmental values of the two foods.
- Users can add/remove columns based on nutritional and environmental wants or needs.
- Raw Data Comparison is available at the bottom of the page, providing the same information in table form.

### 4. NutriSubstitutes (`substitution_dashboard.html`)
Helps users the most nutritionally similar products based on a comprehensive profile including energy, protein, fat, carbohydrates, and key vitamins and minerals.
- User can select food group and specific food in this group.
- K-Nearest Neighbors (KNN) algorithm is used to identify the three most similar products within the same group based on macronutrients, vitamins and minerals the foods contain.

### 5. Food Quiz (`quiz.html`)
A quiz that can be used in an interactive way for educational purposes. The quiz helps users learn about the differences between food items based on nutritional values (like protein and vitamins) and envrionmental impact (like CO2 emissions and water consumption)  
It allows users to:
- Select a focus area to decide the type of quiz (Environmental Impact, Nutritional Value, and a combination of these two).
- Build a custom quiz based on specific comparisons.
- Decide the amount of quiz questions asked/the quiz length.
The quizzes consist of:
- Multiple-choice questions comparing two foods
- Comprehensive pie charts showcasing the comparison between two food items for each question asked.

### 6. Range Filter (`semantic_filter.html`)
Allows users to filter food groups by envrionment and full nutrition per 100 grams, based on specific numeric ranges the users specify, e.g.:
- The user can specify that from the Bread food group, only products containing between 5 to 15 grams of protein are shown, which have a CO2 emissions that is not higher than 0.15 kilo's.
Results are shown in a table and the tool itself works based on an **ontology (RDF/OWL)**, enabling the use of filtering and semantic search.

### 7. About Us (`about_us.html`)
Introduces the project creators' story, the project goal, and the significant factors in the project.

---

## Technologies

- **HTML5, CSS3, JavaScript (Vanilla JS)**
- **Tailwind CSS** – styling and responsive layout
- **Font Awesome** – icons for food categories and UI elements
- **Chart.js** – radar chart visualization in the comparison dashboard
- **Select2 + jQuery** – searchable dropdowns
- **RDF/OWL** - ontology structure for food data, enables range filtering
- **Comunica Engine + SPARQL** – query processing for ontology-based filters
- **Python (scikit-learn)** – used offline for the KNN substitute recommendations
- **CSV dataset (DataClean.csv)** – the unified data source

---

## File Structure

```
Eathical/
│
├── index.html                     # Homepage
├── food_explorer_dashboard.html   # Data Explorer
├── comparison_dashboard_final_v3Clean.html  # Comparison Tool
├── substitution_dashboard.html    # Substitute Goods Analyzer
├── semantic_filter.html           # Range Filter Tool
├── quiz.html                      # Sustainable Food Quiz
│
├── assets/                        # CSS, JS, and icon files
├── DataClean.csv                  # Combined NEVO + LCA dataset
└── README.md                      # (You are here)
```

---

## Data Quality

All data used in Eathical come from two Dutch official, publicly documented databases, both developed by the Rijksinstituut voor Volksgezondheid en Milieu (RIVM).  
Both datasets comply with international standards (ISO 14040, 14044, and EuroFIR).

---

## Descriptive information

**Project Authors**
- Jesse Brouwer
- Liv Komen
- Moad Matoug
- Tatum van Schooneveld  

**Institution**  
University of Amsterdam  

**Programme**  
Master Information Studies - Information Systems Track 
