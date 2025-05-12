
# Who Are We?  Exploring the Ethnic Evolution of Our Ancestors
### Identify and predict patterns in migration of ancestors by time period and country. 

![1000 years of Migration](https://github.com/user-attachments/assets/479022e4-a12d-4cd9-ac84-75809e49cc08)


## Learning objective / Business Understanding
Our ethinic identity is normally defined by a specific country or region our ancestors came from.  However, for many people their ancestors came from multiple countries and regions as peoples migrated and intermarried.  This is reflected in DNA tests which list multiple countries of origin for specfic gene traits.  But what was the path that lead from these countries of origin to who I am today?  That path is recorded in our family history, the genealogy of the line of ancestors going from us to these countries of origin.  Unlike DNA tests, our genealogy doesn't come with a one-page summary of all the steps from the past to the present.   

While most ancestors lived in the same location all their lives, at certain periods in history in certain countries family groups or individuals would move to a new country.  Visualizing the times and places of these major changes in ancestors lives can give insight into the life experiences that shaped their lives and lead to the places and times we now live in.  Genealogy records of life events such as birth and death dates and locations give the raw data for identifying these inflection points in our family's path.  However, this genealogy data is not in a consistent standard format, locations have changed names over the years and boundaries of countries have shifted, and many records give only dates but lack location.  

This project makes a first step in filling out the gaps in ancestor records by modeling the patterns of which time periods and which locations were more likely to have movement from ancestral homelands.  Specific business questions addressed include:
- Which countries were the home location ancestors originated from?
- Which countries had the highest numbers of ancestors who migrated to other countries?
- Which time periods had the highest numbers of ancestors who migrated to other countries?

## Data Sources / Data Understanding
Family history compiled, cleaned, labeled, merged, and analyzed from multiple sources from 2009 - 2024, and summarized in https://github.com/mtmssteffen/WhoAreWe

 - `Ancestor_data.csv`:  Genealogy of ancestors, uniquely ID each individual, giving family surname, gender, birth & death year & location, IDs of parents, and an intepretation of the country of origin.  FamilySearch.com is the original source for the majority of the genealogy records, with some coming from BillionGraves.com, Ancestry.com, MyHeritage.com.  RootsMagic.com provide tools for extracting genealogy data and compiling in text csv files for analysis.
 - `FamilyAtlasPlacesGeocode.csv`:  List of raw locations from Ancestor_data run through the Family Atlas geocoding tool to generate standard location names and latitute-longitude.  About half of the raw locations had automated matches, and close matches required manual review and updating.  The Family Atlas tools is provided by RootsMagic.com
- `DSN-Project-2-6.ipynb`: Jupyter notebook with the complete CRISP-DM process including Business Understanding, Data Understanding, Data Preparation, Modeling, Evaluation, Deployment
- `amap.mp4`:  Animation of Estimated Country data from the Ancestor_data.csv file for comparison with the analysis and models created by this project.

### Ancestor Relationships Representation for Modeling

![Lineage Graph](https://github.com/user-attachments/assets/f41f7af4-746f-4521-b51f-8b5ece9c2990)



## Visualizing migration 

![scatter charts](https://github.com/user-attachments/assets/7f0a722b-40dd-4cdb-bd1c-5a4782663d81)


## Visualizing migration over time

![scatter charts by century](https://github.com/user-attachments/assets/e66dc1d7-c79b-431e-bc9a-69024c05578f)



