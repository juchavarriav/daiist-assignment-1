# Assignment 1 Report

*Delete this italic guidance as you fill in each section. You'll be asked to
defend any of this without your code in front of you — write only what you
can actually explain.*

- **Name**: Juan C Chavarria
- **Student ID**: 19313
- **Email**: jchavarria.ieu2022@student.ie.edu
- **Group**: BBADBA 5B 

## Dataset

*What is it, where did you get it, what does one row represent, how many
rows/columns, and why did you pick it.*

## Business / real-life framing

This model would be used by the operations team of the company that runs the bike stations in the city. They would use it to decide how many bikes to have available in the next hours. Each row in the data is the total number of rentals in the whole system in one hour, so the model tells us how much demand to expect, not where to put the bikes.

Predicting too low is worse than predicting too high. If we predict too low, there may be no bikes at the stations and we lose customers. If we predict too high, we only have some idle bikes, which costs much less.

Because the model is meant to predict future hours, the data is split by time and not randomly. Training is January 2011 to June 2012, validation is July to September 2012 (used to choose the learning rate and the regularization), and test is October to December 2012, used only once at the end. A random split would be cheating because the hour next to a test hour could be in the training set, and neighboring hours are almost the same, so the test would be too easy.

The main metric is MAE, the average number of bikes the model misses by in one hour, which is easy to explain. I also report RMSE, which punishes big misses more, like in rush hour. MAE and RMSE treat predicting too low and too high the same, so I also report the average signed error (actual minus predicted, positive means too low) and the share of hours where the model predicts too low, to check the error that matters most.

## Data preparation & feature engineering

*What you engineered and why, and any data-quality decisions you made along
the way — e.g. "segment X had defective data, so I excluded it and used a
population-average default for scope Y at inference time; the impact of
that choice is Z."*

## Modeling: three implementations, one model

*Which model (linear or logistic regression) and why. A results table
comparing scikit-learn, the manual PyTorch loop, and the standard
torch.nn.Module/torch.optim workflow, on the same test set, against the
naive baseline. Do the three agree? If not, why not?*

## Limitations & next steps

*Real limitations you found, and concretely how you'd address each one with
more time or data — not generic hedging.*

## Generative AI use disclosure

*Per the syllabus AI Policy: what you used and how, or "no AI content used."*
