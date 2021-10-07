# -*- coding: utf-8 -*-
"""
Created on Tue Mar 23 13:54:09 2021

@author: hande
"""

import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

crime = pd.read_csv("crime.csv", index_col=0)
print(crime)

pd.set_option("display.max_columns", 999)

print(crime.head())
print(crime.tail())

crime.info()
crime.describe()

print(crime["Rape"])

print(crime[["Total_crimes", "Rape"]])

print(crime.loc['01.01.2003':'01.12.2003',["Total_crimes", "Rape"]])

crime = pd.read_csv("crime.csv")
print(crime)
sum_total_crimes = crime["Total_crimes"].sum()
print("Total crimes:",sum_total_crimes)



total_serious = crime["Serious"].sum()
print("Total serious crimes:",total_serious)
serious_in_crimes = round(((total_serious)/(sum_total_crimes))*100,1)
print("Ratio of serious crimes:",serious_in_crimes)


total_huge_damage = crime["Huge_damage"].sum()
print("Total huge damage:",total_huge_damage)
huge_damage_in_crimes = round(((total_huge_damage)/(sum_total_crimes))*100,1)
print("Ratio of huge damage:",huge_damage_in_crimes)


total_ecological = crime["Ecological"].sum()
print("Total ecological crimes:",total_ecological)
ecological_in_crimes = round(((total_ecological)/(sum_total_crimes))*100,1)
print("Ratio of ecological crimes:",ecological_in_crimes)


total_terorism = crime["Terrorism"].sum()
print("Total Terrorism:",total_terorism)
terrorism_in_crimes = round(((total_terorism)/(sum_total_crimes))*100,1)
print("Ratio of terrorism:",terrorism_in_crimes)


total_extremism = crime["Extremism"].sum()
print("Total extremism:",total_extremism)
extremism_in_crimes = round(((total_extremism)/(sum_total_crimes))*100,2)
print("Ratio of extremism:",extremism_in_crimes)


total_murder = crime["Murder"].sum()
print("Total murder:",total_murder )
murder_in_crimes = round(((total_murder)/(sum_total_crimes))*100,1)
print("Ratio of murder:",murder_in_crimes)


total_harm_to_health = crime["Harm_to_health"].sum()
print("Total harm to health:",total_harm_to_health)
harm_to_health_in_crimes = round(((total_harm_to_health)/(sum_total_crimes))*100,1)
print("Ratio of harm to health:",harm_to_health_in_crimes)


total_rape = crime["Rape"].sum()
print("Total rape:",total_rape)
rape_in_crimes = round(((total_rape)/(sum_total_crimes))*100,2)
print("Ratio of rape:",rape_in_crimes)


total_theft = crime["Theft"].sum()
print("Total theft:",total_theft)
theft_in_crimes = round(((total_theft)/(sum_total_crimes))*100,1)
print("Ratio of theft:",theft_in_crimes)


total_vehicle_theft = crime["Vehicle_theft"].sum()
print("Total vehicle theft:",total_vehicle_theft)
vehicle_theft_in_crimes = round(((total_vehicle_theft)/(sum_total_crimes))*100,1)
print("Ratio of vehicle theft:",vehicle_theft_in_crimes)


total_fraud_scam = crime["Fraud_scam"].sum()
print("Total fraud scam:",total_fraud_scam)
fraud_scam_in_crimes = round(((total_fraud_scam)/(sum_total_crimes))*100,1)
print("Ratio of fraud scam:",fraud_scam_in_crimes)


total_hooligan = crime["Hooligan"].sum()
print("Total hooligan:",total_hooligan)
hooligan_in_crimes = round(((total_hooligan)/(sum_total_crimes))*100,1)
print("Ratio of hooligan:",hooligan_in_crimes)


total_drugs = crime["Drugs"].sum()
print("Total drugs:",total_drugs)
drugs_in_crimes = round(((total_drugs)/(sum_total_crimes))*100,1)
print("Ratio of drugs:",drugs_in_crimes)

total_weapons = crime["Weapons"].sum()
print("Total weapons:",total_weapons)
weapons_in_crimes = round(((total_weapons)/(sum_total_crimes))*100,2)
print("Ratio of weapons:",weapons_in_crimes)


np.set_printoptions(suppress=True)
y = np.array([serious_in_crimes,huge_damage_in_crimes,ecological_in_crimes,terrorism_in_crimes,extremism_in_crimes,murder_in_crimes,harm_to_health_in_crimes,rape_in_crimes,theft_in_crimes,vehicle_theft_in_crimes,fraud_scam_in_crimes,hooligan_in_crimes,drugs_in_crimes,weapons_in_crimes])
mylabels = ["Serious", "Huge damage", "Ecological", "Terrorism", "Extremism", "Murder", "Harm to health", "Rape", "Theft", "Vehicle theft","Fraud scam", "Hooligan", "Drugs", "Weapons"]
plt.title("Crimes in Russia")
myexplode = [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]

colors = ["crimson", "mediumvioletred", "darkmagenta", "plum", "lightskyblue", "midnightblue", "lightseagreen", "turquoise", "springgreen", "seagreen", "gold", "darkorange", "orangered", "firebrick"]

fig1, ax1 = plt.subplots()
myexplode = [0, 0, 0, 0, 0, 0, 0, 0, 0.1, 0, 0, 0, 0, 0]

ax1.pie(y, colors = colors, explode = myexplode, labels = mylabels, autopct = "%1.1f%%", shadow = True, startangle = 0)
plt.show()

plt.pie(y, labels = mylabels, explode = myexplode, autopct = "%1.1f%%", shadow = True)

plt.show()


"""
np.set_printoptions(suppress=True)

y = np.array([serious_in_crimes, ecological_in_crimes, rape_in_crimes, huge_damage_in_crimes, terrorism_in_crimes,
              theft_in_crimes, extremism_in_crimes, murder_in_crimes, harm_to_health_in_crimes, vehicle_theft_in_crimes,fraud_scam_in_crimes,hooligan_in_crimes,drugs_in_crimes,weapons_in_crimes])

mylabels = ["Serious", "Ecological", "Rape", "Huge Damage", "Terrorism", "Theft", "Extremism", "Murder", "Harm to Health", "Vehicle Theft", "Fraud Scam", "Hooligan", "Drugs", "Weapons"]

plt.title("Crimes in Russia")

plt.pie(y, labels = mylabels)
plt.show()


np.set_printoptions(suppress=True)

y = np.array([serious_in_crimes, ecological_in_crimes, huge_damage_in_crimes, terrorism_in_crimes,
              theft_in_crimes, extremism_in_crimes, murder_in_crimes, harm_to_health_in_crimes, vehicle_theft_in_crimes,fraud_scam_in_crimes,hooligan_in_crimes,drugs_in_crimes,weapons_in_crimes,rape_in_crimes])

mylabels = ["Serious", "Ecological", "Huge Damage", "Terrorism", "Theft", "Extremism", "Murder", "Harm to Health", "Vehicle Theft", "Fraud Scam", "Hooligan", "Drugs", "Weapons", "Rape"]
mysizes = []
plt.title("Crimes in Russia")

plt.pie(y, labels = mylabels)
plt.show()
sizes = [30, 25, 5, 1, 3, 7, 3, 45, 3, 10, 3, 9, 6, 2]

"""

np.set_printoptions(suppress=True)

y = np.array([serious_in_crimes, ecological_in_crimes, extremism_in_crimes, harm_to_health_in_crimes, huge_damage_in_crimes, 
              rape_in_crimes, terrorism_in_crimes, murder_in_crimes, theft_in_crimes,vehicle_theft_in_crimes,fraud_scam_in_crimes,hooligan_in_crimes,drugs_in_crimes,weapons_in_crimes ])
mylabels = ["Serious", "Ecological", "Extremism", "Harm to Health", "Huge Damage", "Rape", "Terrorism", "Murder", "Theft", "Vehicle theft","Fraud scam", "Hooligan", "Drugs", "Weapons"]
colors = ["crimson", "mediumvioletred", "darkmagenta", "plum", "lightskyblue", "midnightblue", "lightseagreen", "turquoise", "springgreen", "seagreen", "gold", "darkorange", "orangered", "firebrick"]
plt.title("Crimes in Russia")
myexplode = [0, 0, 0.1, 0.2, 0, 0.3, 0.2, 0, 0.1, 0, 0, 0, 0, 0]
plt.pie(y, labels = mylabels, colors = colors, explode = myexplode, autopct = "%1.2f%%", pctdistance = 0.6 , shadow = True )
plt.show()




np.set_printoptions(suppress=True)

y = np.array([serious_in_crimes, ecological_in_crimes, extremism_in_crimes, huge_damage_in_crimes, 
              rape_in_crimes, terrorism_in_crimes, murder_in_crimes, theft_in_crimes, harm_to_health_in_crimes, vehicle_theft_in_crimes,fraud_scam_in_crimes,hooligan_in_crimes,drugs_in_crimes,weapons_in_crimes ])
mylabels = ["Serious", "Ecological", "Extremism", "Huge Damage", "Rape", "Terrorism", "Murder", "Theft", "Harm to Health", "Vehicle theft","Fraud scam", "Hooligan", "Drugs", "Weapons"]
colors = ["crimson", "mediumvioletred", "darkmagenta", "plum", "lightskyblue", "midnightblue", "lightseagreen", "turquoise", "springgreen", "seagreen", "gold", "darkorange", "orangered", "firebrick"]
plt.title("Crimes in Russia")
myexplode = [0, 0, 0.1, 0.2, 0, 0.3, 0.2, 0, 0.1, 0, 0, 0, 0, 0]
plt.pie(y, labels = mylabels, colors = colors, explode = myexplode, autopct = "%1.2f%%", pctdistance = 0.6 , shadow = True )
plt.show()


np.set_printoptions(suppress=True)

y = np.array([serious_in_crimes, extremism_in_crimes, huge_damage_in_crimes, 
              terrorism_in_crimes, rape_in_crimes, murder_in_crimes, theft_in_crimes, ecological_in_crimes, harm_to_health_in_crimes, vehicle_theft_in_crimes,fraud_scam_in_crimes,hooligan_in_crimes,drugs_in_crimes,weapons_in_crimes ])
mylabels = ["Serious", "Extremism", "Huge Damage", "Terrorism", "Rape", "Murder", "Theft", "Ecological", "Harm to Health", "Vehicle theft","Fraud scam", "Hooligan", "Drugs", "Weapons"]
colors = ["crimson", "mediumvioletred", "darkmagenta", "plum", "lightskyblue", "midnightblue", "lightseagreen", "turquoise", "springgreen", "seagreen", "gold", "darkorange", "orangered", "firebrick"]
plt.title("Crimes in Russia")
myexplode = [0, 0.11, 0, 0.4, 0.1, 0.3, 0.1, 0.2, 0.1, 0, 0, 0, 0, 0]
plt.pie(y, labels = mylabels, colors = colors, explode = myexplode, autopct = "%1.2f%%", pctdistance = 0.6 , shadow = True )
plt.show()


np.set_printoptions(suppress=True)

y = np.array([serious_in_crimes, extremism_in_crimes, huge_damage_in_crimes, 
              terrorism_in_crimes, rape_in_crimes, theft_in_crimes, ecological_in_crimes, harm_to_health_in_crimes, vehicle_theft_in_crimes,fraud_scam_in_crimes,hooligan_in_crimes,drugs_in_crimes,weapons_in_crimes, murder_in_crimes ])
mylabels = ["Serious", "Extremism", "Huge Damage", "Terrorism", "Rape", "Theft", "Ecological", "Harm to Health", "Vehicle theft","Fraud scam", "Hooligan", "Drugs", "Weapons", "Murder",]
colors = ["crimson", "mediumvioletred", "darkmagenta", "plum", "lightskyblue", "midnightblue", "lightseagreen", "turquoise", "springgreen", "seagreen", "gold", "darkorange", "orangered", "firebrick"]
plt.title("Crimes in Russia")
myexplode = [0, 0.11, 0, 0.4, 0.1, 0.3, 0.1, 0.2, 0.1, 0, 0, 0, 0, 0.3]
plt.pie(y, labels = mylabels, colors = colors, explode = myexplode, autopct = "%1.2f%%", pctdistance = 0.6 , shadow = True )
plt.show()


np.set_printoptions(suppress=True)

y = np.array([serious_in_crimes, extremism_in_crimes, huge_damage_in_crimes, 
              terrorism_in_crimes, rape_in_crimes, theft_in_crimes, murder_in_crimes, ecological_in_crimes, harm_to_health_in_crimes, vehicle_theft_in_crimes,fraud_scam_in_crimes,hooligan_in_crimes,drugs_in_crimes,weapons_in_crimes])
mylabels = ["Serious", "Extremism", "Huge Damage", "Terrorism", "Rape", "Theft", "Murder", "Ecological", "Harm to Health", "Vehicle theft","Fraud scam", "Hooligan", "Drugs", "Weapons"]
colors = ["crimson", "mediumvioletred", "plum", "darkmagenta","midnightblue", "lightskyblue", "lightseagreen", "turquoise", "springgreen", "seagreen", "gold", "darkorange", "orangered", "firebrick"]
plt.title("Crimes in Russia")
myexplode = [0.1, 0.11, 0.1, 0.4, 0.12, 0.1, 0.3, 0.2, 0.1, 0, 0, 0, 0, 0]
plt.pie(y, labels = mylabels, colors = colors, explode = myexplode, autopct = "%1.2f%%", pctdistance = 0.6 , shadow = True )
plt.show()



np.set_printoptions(suppress=True)

y = np.array([serious_in_crimes, extremism_in_crimes, huge_damage_in_crimes, 
              terrorism_in_crimes, theft_in_crimes, rape_in_crimes, murder_in_crimes, ecological_in_crimes, harm_to_health_in_crimes, vehicle_theft_in_crimes,fraud_scam_in_crimes,hooligan_in_crimes,drugs_in_crimes,weapons_in_crimes])
mylabels = ["Serious", "Extremism", "Huge Damage", "Terrorism", "Theft", "Rape", "Murder", "Ecological", "Harm to Health", "Vehicle theft","Fraud scam", "Hooligan", "Drugs", "Weapons"]
colors = ["crimson", "mediumvioletred", "plum", "darkmagenta", "lightskyblue","midnightblue",  "lightseagreen", "turquoise", "springgreen", "seagreen", "gold", "darkorange", "orangered", "firebrick"]
plt.title("Crimes in Russia")
myexplode = [0.1, 0.11, 0.1, 0.1, 0.1, 0.4, 0.3, 0.2, 0.1, 0, 0, 0, 0, 0]
plt.pie(y, labels = mylabels, colors = colors, explode = myexplode, autopct = "%1.2f%%", pctdistance = 0.6 , shadow = True )
plt.legend(bbox_to_anchor=(-0.7,1), loc = "upper left", title = "Crimes:")
plt.show()


np.set_printoptions(suppress=True)

y = np.array([serious_in_crimes, extremism_in_crimes, huge_damage_in_crimes, 
              terrorism_in_crimes, theft_in_crimes, rape_in_crimes, murder_in_crimes, ecological_in_crimes, harm_to_health_in_crimes, vehicle_theft_in_crimes,fraud_scam_in_crimes,hooligan_in_crimes,drugs_in_crimes,weapons_in_crimes])
mylabels = ["Serious", "Extremism", "Huge Damage", "Terrorism", "Theft", "Rape", "Murder", "Ecological", "Harm to Health", "Vehicle theft","Fraud scam", "Hooligan", "Drugs", "Weapons"]
colors = ["crimson", "mediumvioletred", "plum", "darkmagenta", "lightskyblue","midnightblue",  "lightseagreen", "turquoise", "springgreen", "seagreen", "gold", "darkorange", "orangered", "firebrick"]
plt.title("Crimes in Russia")
myexplode = [0.1, 0.11, 0.1, 0.1, 0.1, 0.4, 0.3, 0.2, 0.1, 0, 0, 0, 0, 0]
plt.pie(y, colors = colors, explode = myexplode, autopct = "%1.2f%%", pctdistance = 0.6 , shadow = True )
plt.legend(labels = mylabels, bbox_to_anchor=(-0.7,1), loc = "upper left", title = "Crimes:")
plt.show()

