# Details on the SMART data (from BRFSS)

The Centers for Disease Control analyzes Behavioral Risk Factor Surveillance System (BRFSS) survey data for specific metropolitan and micropolitan statistical areas (MMSAs) in a program called the Selected Metropolitan/Micropolitan Area Risk Trends of BRFSS (SMART BRFSS.)

In this work, we will focus on data from the 2016 SMART, and in particular on data from the Cleveland-Elyria, OH, Metropolitan Statistical Area. The purpose of this survey is to provide localized health information that can help public health practitioners identify local emerging health problems, plan and evaluate local responses, and efficiently allocate resources to specific needs.

# The Cleanup

The smart.html file (and the smart.Rmd file that creates it) produces several "clean" data sets from the SAS transport file provided by BRFSS in August 2017.

The data files produced by smart.html include:

- smart_ohio.csv which includes data on 57 variables for 6014 subjects in five MMSAs in Ohio.
- smartcle.csv which includes data on those same 57 variables for the 1036 subjects in the Cleveland-Elyria-Lorain OH MMSA.
- smartcle1.csv which includes a subset of 11 variables for those same 1036 subjects.

We've used the smartcle1 data in our Course Notes, and in several presentations in class.

