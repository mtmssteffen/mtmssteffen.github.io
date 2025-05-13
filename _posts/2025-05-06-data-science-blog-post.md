
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
The genealogy data used in this project is from Family history compiled, cleaned, labeled, merged, and analyzed from multiple sources from 2009 - 2024, and summarized in https://github.com/mtmssteffen/WhoAreWe in the following files:

 - `Ancestor_data.csv`:  Genealogy of ancestors, uniquely ID each individual, giving family surname, gender, birth & death year & location, IDs of parents, and an intepretation of the country of origin.  FamilySearch.com is the original source for the majority of the genealogy records, with some coming from BillionGraves.com, Ancestry.com, MyHeritage.com.  RootsMagic.com provide tools for extracting genealogy data and compiling in text csv files for analysis.
 - `FamilyAtlasPlacesGeocode.csv`:  List of raw locations from Ancestor_data run through the Family Atlas geocoding tool to generate standard location names and latitute-longitude.  About half of the raw locations had automated matches, and close matches required manual review and updating.  The Family Atlas tools is provided by RootsMagic.com
- `DSN-Project-2-6.ipynb`: Jupyter notebook with the complete CRISP-DM process including Business Understanding, Data Understanding, Data Preparation, Modeling, Evaluation, Deployment
- `amap.mp4`:  Animation of Estimated Country data from the Ancestor_data.csv file for comparison with the analysis and models created by this project.

## Exploratory Data Analysis / Data Preparation

### When did these ancestors live?
Number of ancestors by century:

![image](https://github.com/user-attachments/assets/89445a09-2c05-405a-814b-24c54775fe37)

This data is not "normally distributed" - each tail on the histogram has a different root cause.  The right tail reflect the exponential growth as you go back in time:  1 child -> 2 parents - > 4 grandparents -> 16 greatgrandparents....  The left tail reflects 2 factors:  1) the lack of historical records, i.e. the genealogy comes to a roadblock and ends even though the ancestors did exist, and 2) going back more than 6-12 generations there starts to be common ancestors - a 10th great grandparent appears as the ancestor to multiple lines; this is especially true for small communities in medival and earlier times where every marriage candidate was related as a 5th, 6th, .... cousin.

### Where did these ancestors live?

Migrations occured throughout history, so there is no one place where these ancestors lived continuously for 2000 years.  Therefore the countries where ancestors lived are best understood by time periods:

![image](https://github.com/user-attachments/assets/be8ee8ff-7f16-48ce-a5fc-82ba07bb8fe6)


## Modeling 
### Ancestor Relationships Representation for Modeling Migration

#### Identifying Migration in Ancestor Data

The current ancestor data does not have explicit records of migration, i.e. "Arrived at Ellis Island on September 26, 1903".  In addition, the death locations have a high level of missing data, making it hard to infer migration by comparing birth and death locations.  So migration is inferred by comparing the birth locations of a parent and child - if they are different, then the parent migrated from his or her birth country to the child's birth country.  To identify these points of migration, the relationships between ancestors must be directly represented:

![Lineage Graph](https://github.com/user-attachments/assets/f41f7af4-746f-4521-b51f-8b5ece9c2990)

## Evaluation

### Visualizing migration 

Plotting the parent country (X Axis) versus the child country (Y Axis) displays the inferred migrations between countries.  The majority of ancestors are on the diagonal, meaning they did not migrate, which shows the relative proportions of ancestors who did and did not migrate.

![scatter charts](https://github.com/user-attachments/assets/7f0a722b-40dd-4cdb-bd1c-5a4782663d81)

Removing the individuals who did not migrate gives a clearer picture of the migration patterns.  Note that migrations were not a one way, linear path from the "Old World" to the "New World"; migrations moved in many directions to and from each country.  So the definition of "ethinic identity" becomes a mix of many countries of origin:

![migration scatter charts](https://github.com/user-attachments/assets/081765c4-417b-4e69-a347-34fb9019551c)

### Visualizing migration over time

As previously discussed, no family groups lived in one country continously through 2000 years.  So to see the actual patterns of migration, the migration visualization needs to be plotted by time periods.

![migration scatter charts by century](https://github.com/user-attachments/assets/a888a3c6-af60-40cd-8a11-850773134a37)




## Summary of Results

### Which countries were the home location ancestors originated from?
England has the highest number of ancestors by almost an order of magnitude over the next largest country France, but there is not a linear sequence from England to the present day United States.  Different branches of ancestors came from a variety of countries, and migrated to and from England in multiple periods of time over the past 2000 years.

### Which countries had the highest numbers of ancestors who migrated to other countries?
Again, England has the overall highest number of ancestors migrating both from and to the country, but this varied over time, and England had more incoming than outgoing - 836 vs 685

### Which time periods had the highest numbers of ancestors who migrated to other countries?
The years 1000 - 1099 had the highest absolute number of migration - 347, but the early centuries between 100 - 1000 all had higher percentages of the population migrate.  This is probably because records are few for these centuries and skewed towards historical people, monarchies, leaders, royal lines, etc.
The years 1600 - 1700 were very close to the years 1000 - 1099 at 32% migration, and because of their place in history this period is the most representative of the "common people" who had to make the decision to leave their homeland and move to another country.
