# Readme
This repository has the functionality to download current vaccination data and data on planned vaccine deliveries for Germany.

Based on this a forecast is developed which 
1. predicts when, how many 1st or 2nd doses of the different vaccines are vaccinated
2. when which effect is reached on the herd immunity

# Result examples

To demonstrate examples of the output have a look on these images which are a direct output of the Corona-Vaccination-Calculator.ipynb 
Notebook.

![vaccinations_per_week](corona_results/vaccinations_per_week.png)

![vaccinations_total](corona_results/vaccinations_total.png)

The following text as well is an example output of the corona-jupyter-notebook just mentioned:

![result_text](corona_results/result_text.jpg)


# Assumptions

- The effect of the different doses of the different vaccines take place two weeks after vaccination
- The 2nd dose of Moderna and Biontech are vaccinated 5 weeks after the first one. The 2nd dose of Astra Zeneca is vaccinated 12 weeks after the first one.
  (An analysis which led me to the last two assumptions is made in the Corona-Vaccination-Calculator-Notebook in the part 
  "2nd analysis - how much time between the first and the second dose per vaccine".)
- Currently the following effects are assumed to take place 14 days after the first dose of Biontech, Moderna, Astra Zeneca 
  and Johnson & Johnson: 82 %, 70 %, 76 % and 66 %.
- Two weeks after the second dose an effect of 95 % (Biontech), 94 % (Moderna) and 82 % (Astra Zeneca) is assumed.
- The deliveries of one week will be vaccinated one week later.
- The vaccine stocks of the country do stay constant.
- If deliveries in the week before are smaller then the assumed 2nd dose, then the later is reduced to the amount delivered. 
Since this reduction is not yet placed in the next buckets the number of persons with 2nd dose is predicted to low while the one with just one dose is to low.
- Cross vaccinations (e.g. 1st Astra Zeneca then Biontech) are not taken into account.

# How to

- Start and run the Notebook Corona-Vaccination-Calculator.
- Several information will be presented to you in table or text form. (graphs shall follow)

# Files

- Corona-Vaccination-Calculator.ipynb: main calculations.
- tools.py: functions which are helpful not just in this repository.
- corony.py: specific analysis-functions for this notebook.
- README.md: as usual
- .gitignore: as usual

# Status

- Currently the download and the data preparation is just prepared for the situation in Germany.
- Assumptions are not yet completely described.
- Links for the effects are not yet all in this readme.
- Links to the original studies need to be added.
- No graphs generated yet

# Sources + links
The relevant results from studies on which the assumptions are based and the associated links will be presented here.

### Astra
Thus, the studies in the UK, Brazil and South Africa showed the efficacy of the vaccine at the level of 76% after the first dose with protection maintained to the second dose. With an interval of 12 weeks between them and more, the efficacy of the vaccine increases up to 82%.
the studies confirmed that AstraZeneca vaccine reduces asymptomatic transmission of the virus by 67% after the first dose and by 50% after the second
https://112.international/society/astrazeneca-vaccine-is-effective-after-first-dose-58667.html

### Sinopharm
14 days post 2nd dose: 78.1%
Peer-reviewed results published in JAMA of Phase III trials in United Arab Emirates and Bahrain showed BBIBP-CorV 78.1% effective against symptomatic cases and 100% against severe cases (21 cases in vaccinated group vs. 95 cases in placebo group).

"This prespecified interim analysis of a randomized clinical trial included 40 382 participants who received at least 1 dose of a 2-dose inactivated vaccine series developed from either SARS-CoV-2 WIV04 (5 µg/dose) or HB02 (4 µg/dose) strains or an aluminum hydroxide–only control, with a primary end point of the incidence of symptomatic COVID-19 at least 14 days after the second injection. The efficacy for the 2 vaccines, compared with an aluminum hydroxide–only control, was 72.8% in the WIV04 group and 78.1% in the HB02 group; both comparisons were statistically significant."
https://jamanetwork.com/journals/jama/fullarticle/2780562