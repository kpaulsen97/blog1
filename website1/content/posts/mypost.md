---
title: "Mortality, emissions, global warming: energy type point of view"
date: 2022-05-07T09:08:10+02:00
---

# Introduction
Energy: it's the base of everything. If we didn't have available energy our cars wouldn't work, our industries neither, we wouldn't have water in our houses, warmth in the winter and the list goes on. <br>


But everything has a cost, especially if it is this great: the planet is suffering. And doesn't matter if we can order sushi from our smartphones whenever we want if we don't have a planet to eat sushi on. 

A very common solution we hear all the time: reduce energy consumption. We change kind of electronics to more sustainable ones, we remember to turn off the lights when we go out of a room, we kindly asks big corporations to reduce emissions in their factories etc <br>

But let's be honest here: is it working? Are humans really capable of such big changes in their lifestyles for such an abstract motive? 
By current statistics we are severly far away from the plans to reduce world emissions, even if this issue has been talked for decades. 

So what if we just changed the type of energy used? What if we didn't have to change our lifestyle, as this appears to have not been working, but we just had to invest in a different kind of energy? Would that suffice? 

So we will structure our analysis in the following way: first we will analyze the link between global warming and emissions, then emissions and energy type, and finally we will determine how an ideal proportions of energy type will affect mortality. 

# Exploratory data analysis: Temperatures

![demo](/website1.github.io/d1.png)
![demo](/website1.github.io/d2.png)

We can see in the above images how the change of temperature is a very real phenomena: in the first two plot we can see how there has been an significant average difference of temperature from a pre-industrial baseline year by year. 

In the plots that follows we can see how in every continent the increase appears to be linear: every year there appears to be an costant increment, with Asia displaying the highest increase, and Oceania the lowest. So we have to admit that year by year we are inesorably increasing the earth temperature, with all it's negative consequences. 

# Exploratory Data Analysis: Emissions

![demo](/website1.github.io/d4.png)
With the above pictures we have a hint of a pattern that starts to emerge: from the plots before we can tell how the temperatures have been rising, and from these two above we can see how both the energy expenditure per capita and the emissions have been increasing. 

So there seem to be three key playiers: the energy expenditure, the temperatures and the emissions. 

![demo](/website1.github.io/d5.png)

Above there is a plot of the emissions by country in year 2019: we can see how there is a profound difference between countries, with USA and China leading by far in terms of emissions. So let's have a closer look in the differnece between emission reduction in recent years. 

![demo](/website1.github.io/d6.png)
Emissions are reducing in first world countries, especially in scandinavian countries as Denmark and Sweden, but are increasing dramatically in third world and developing countries, such as India, China and the African continent. 

Can the change of energy type have been responsible for this? Let's see it in the following interactive plot.

# Exploratory Data Analysis: Energy type

Below you will find two interactive plots. Just by selecting or deselecting in the legend the type of energy, you will have visualizations accordingly: for example, just by ticking Oil, you will have visualizations regarding the oil energy percentage of a certain country.

{{< include-html "content/posts/india.html" >}}
India, which had the biggest increase in emissions in the last 30 years, appears to be using a high percentage of oil, coal and gas, the energy types with the highest emissions. Negligeble amount of sustainable energy types, with an actual decrease of hydro energy during the years. 

So one of the countries with the highest emissions appears to be using a very low percentage of "green" energy types. What about the country with the lowest emissions per population size, Sweden?

{{< include-html "content/posts/sweden.html" >}}
On the contrary, Sweden managed to keep Coal usage at low, reduced by half the usage of oil, and increased by a lot nuclear energy, wind energy and always had a great percentage of hydro. 

So there appears to be a severe difference in percentage of energy types between the highest and lowest polluter.

# Data Analsysis: Machine Learning Models

To better investigate the relationship between energy type and emission, let's build a classification algorithm that predicts if a country can be considered green on an emission point of view based upon the amount of energy produced per energy type. 

![demo](/website1.github.io/d7.png)

We can see by the plot above how the model is very reliable: it misspredicts just one country out of 16. While based upon feature importance, it appears that the key features are those with the highest emissions. This might lead to thinking that it's irrelevant if a country utilizes or not green energy. But we have a different interpretation: since, for example, nuclear energy has a low degree of emission, it doesn't influence as much the total emissions of a country, therefore it's not relevant in determining if a country is green or not.

To verify if this hypotesis is correct, let's try a different model: one that utilizes the percentage of energy type usage. If our theory is correct, nuclear energy should be an important feature for the model: because in this case having high percentage of nuclear energy would mean low percentage of high emissions energy, like oil, so an overall low emissions values.

![demo](/website1.github.io/d8.png)

This model is even more performative. It never misspredicted any country. And as we suspected, now features as the percentage of Nuclear and Hydro are very important, which is interesting because it's two of the three parameters, with oil, that had the highest difference between Sweden and India. 

So we have strong indicators that the percentage of energy type is a strong indicator of how green is a country based upon emissions. 

So let's assume the whole world had the percentage of energy type as Sweden, and let's see how it would impact the global emissions. 

To determine this, we will build a model that will predict the emissions based upon the energy percentage first and the total amount of energy utilized, and see how it would perform in case we utilized the same amount of energy of the world with the proportions of sweden.

![demo](/website1.github.io/d9.png)

With a 0.1 circa of normalized RMSE, a good measure of model performance, the model predicts a reduction of emissions of circa 86%. 

Now let's build a model that has in input the emissions and in output the temperature anomalies, to determine how this level of predicted emissions would affect global warming.

![demo](/website1.github.io/d10.png)

With a 0.2 circa of normalized RMSE, an acceptable measure of model performance, the model predicts a drop of 97% of temperature anomalies, so an almost total reversal to pre-industrial temperatures.

# Mortality

We have seen how a great deal of nuclear energy, as utilized by Sweden, can be crucial towards lowering emissions. But the objection might come immediate: "isn't it dangerous?". So based upon death by energy type statistics, let's confront the mortality associated with deaths with the current world energy type proportions, with the deaths if the world had the same energy usage of sweden. 

![demo](/website1.github.io/d11.png)
As we can see the total amount of deaths would reduce by 70% circa. But more interestingly, even though sweden has a very high percentage of Nuclear Energy usage, it still appears to have a negligeble amount of mortality. But Coil on the contrary has a very low energy percentage but a high death toll: this is because the long term health effects of breathing coil byproducts and the dangers of its extraction. So the true dangers aren't in the nuclear, but in high emission energy types. 

# Conclusion:

We have witnessed how there is a clear connection between the rising of the temperatures, emissions, energy requirements per capita, and energy type usage. 

But it appears a simple solution could help solve all of these problems: adopting the scandinavian energy proportion usage. 











