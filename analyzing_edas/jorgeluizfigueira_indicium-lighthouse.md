**[source](https://github.com/jorgeluizfigueira/indicium-lighthouse/blob/main/notebooks/Projeto%20Lighthouse.ipynb)**

### Methodologies
- Adopted *[Cross-Industry Standard Process for Data Mining (CRISP-DM)](/topics/CRISP_DM.md)*

## CRISP
1. Business Understanding
	- The objective of the EDA was to build a tool to analyze **Rent Prices on New York**
	- Objective -> ***Answer*** the client with a **effective prediction** of the **rent prices** 
2. Data Understanding
	- Understand the dataset we're working with
		- Irrelevant or relevant variables
		- Statistical summary of the data
		- Null values
		- What each variable is about
	- Variables:
		- `id` -> Unique key for each ad
		- `nome` -> Name of the ad
		- `host_id` -> Identifier of the host
		- `host_name` -> Name of who posted the ad
		- `bairro_group` -> Group of streets the building is located in
		- `bairro` -> Specific street where the building is located in
		- `latitude` 
		- `longitude`
		- `room_type` -> Type of place offered, `private_room`, `whole`, etc.
		- `minimo_noites` -> Minimal amount of nights you can rent
		- `numero_de_reviews` -> Number of reviews 
		- `ultima_review` -> Date of the last received review
		- `reviews_por_mes` -> Amount of reviews it receives per month
		- `calculado_host_listings_count` -> How many listings of the same host
		- `disponibilidade_365` -> Availability throughout the year
	- Step of analysis:
		1. Analyzing if any of the values are empty `isnull().sum()`
		2. Verifying for duplicated values (through the id)
		3. Removal of useless variables -> `host_id` and `host_name`
		4. `.describe(include="number")` and `.describe(exclude="number")`