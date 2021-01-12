# Portfolio Jefry el Bhwash Team Zero

> Jefry el Bhwash
16095065 E
(Electrical Engineering)
11-01-2021

> This portfolio showcases my notable contributions to the team work and also displays the skills I have learned during this minor. It does not show every single notebook I made in the last 16 weeks.

# Project Description:

> What is a suitable model to predict energy use and production of a “Zero At The Meter” dwelling, one day in advance with hourly resolution.

*During the start of the project I've noticed that I was not on the same page with my team concerning the actual goal of this project. Most of them seemed to focus too much on part two, ignoring part one. However part one should be our only focus until we have finished it, since our problem owner is as much after part one as he is after part two. By continuously pointing my team members to the actual goal we finally came to the same vision of the project.*

The project is divided in two parts:

**Part one** is to predict the energy production and energy consumption one day in advance with a resolution of one hour.

If we are done with this and we have weeks to spare, we can go to the next stage ourselves.

**Part two** is to create a model that finds the optimal usage of the energy produced by the solar panels. We do this because at the moment you get paid for selling your energy to the net. In 1-2 years they won't do this, they might even fine people for selling energy when the net is overloaded. So the energy needs to be intelligently bought and sold.

- Do we need it the next day?
- Is it profitable to sell it now and buy energy for a lower price later?

Part two was never realised, however the problem owner seemed more than happy with the final results of this project.

# Courses

[Mandatory Datacamp Courses](Portfolio%20Jefry%20el%20Bhwash%20Team%20Zero%20046897d9242241efaeb7a971eb1eb0e1/Mandatory%20Datacamp%20Courses%20bd178ef8989146139a787fce3c0fca5b.md)

[Other Datacamp Courses](Portfolio%20Jefry%20el%20Bhwash%20Team%20Zero%20046897d9242241efaeb7a971eb1eb0e1/Other%20Datacamp%20Courses%20b5cedbb2f5aa4ee38e1eccbafef9f98b.md)

# Domain Knowledge

[Papers read](Portfolio%20Jefry%20el%20Bhwash%20Team%20Zero%20046897d9242241efaeb7a971eb1eb0e1/Papers%20read%207441464009884688be51cf36937ecbc5.md)

### Terminology used within this portfolio:

**Irradiance:** 
The amount of solar radiation received by a unit area

**Pair Programming:** 
When working on the same script with two people there is often a clear distinction between two roles: 
- The **Driver** who is typing in the code, 
- the **Navigator** who is looking ahead and offering help when needed.

**KNMI:**
Koninklijk Nederlands Meteorologisch Instituut

**Weather data:**
 measurements of a weather station located somewhat close to the houses. 

# Work summary

Since we were all new to this we had to start slow and make sure everybody could keep up.
We started with exploring the data and look into what was already done. 
We chose to start with predicting energy production instead of energy consumption, since that would be an easier and more consistent variable to predict. Then we created some simple and small datasets for the simple models which we slowly expanded while our knowledge and skills grew. Then we moved on with Neural Networks while the lectures were explaining those and finally ended up with an LSTM.

# Work

During this project I:

- made and tweaked a lot of datasets that were used in multiple models,

    [Datasets](Portfolio%20Jefry%20el%20Bhwash%20Team%20Zero%20046897d9242241efaeb7a971eb1eb0e1/Datasets%20e581ab49c64e4a8886f347acd0ecb45c.md)

    A data pre-processing notebook that also does a little exploration since we missed something during the exploration phase.

    [Preprocessing&Exploration](Portfolio%20Jefry%20el%20Bhwash%20Team%20Zero%20046897d9242241efaeb7a971eb1eb0e1/Preprocessing&Exploration%20f1ddb0f73ad449f0a3cacdbee3021e83.md)

- extracted Weather data from KNMI,

    [KNMI Extraction](Portfolio%20Jefry%20el%20Bhwash%20Team%20Zero%20046897d9242241efaeb7a971eb1eb0e1/KNMI%20Extraction%20459f2731e075474fb1ce32107da8826f.md)

- worked with CvanDrunen on an MVLR for Production as a Driver,

    [MVLR Production](Portfolio%20Jefry%20el%20Bhwash%20Team%20Zero%20046897d9242241efaeb7a971eb1eb0e1/MVLR%20Production%200b8223dd22984ed98e541949a2ef3e3a.md)

- worked with CvanDrunen to start with simpler LSTM's as a Driver,
- made an LSTM for consumption after the basic version was done.

    [LSTM](Portfolio%20Jefry%20el%20Bhwash%20Team%20Zero%20046897d9242241efaeb7a971eb1eb0e1/LSTM%20138f0f18a4e24c31a6a4acedecccf587.md)

- Wrote the draft for the introduction of the paper and the results

    [Paper parts](Portfolio%20Jefry%20el%20Bhwash%20Team%20Zero%20046897d9242241efaeb7a971eb1eb0e1/Paper%20parts%20f6103c42afff4e6cbb44f0e474144bf4.md)

- Presentations

    [Presentations](Portfolio%20Jefry%20el%20Bhwash%20Team%20Zero%20046897d9242241efaeb7a971eb1eb0e1/Presentations%2014628f0ba00145c58163c922006ed1d5.md)

# Reflection

I have learned a lot during these 16 weeks and I am very grateful that I was able to get access to this minor! It has confirmed my drive to pursue data science as a career and I will take these lessons further.

### Things I will do better in the future

I am aware that I might shoot myself in the foot by listing everything that I wish I did differently, but these are in my opinion some my most valuable lessons of the past few months.

- Research is about looking into what other people have done, understanding that, replicating that and adding personal experience or knowledge to that, then documenting that so other people can further that knowledge.
    - What I did was looking into what was done, then looking at only the name of the models used and trying to figure out how to make them work on our dataset/situation.
- Some of the models were changed, but then after changing something I did not put enough energy into seeing if it had a positive effect; I mostly did it because 'that's just how it works'
So if it had a small negative effect on the model, I went on with tweaking other parameters.
The last model, the consumption LSTM, was done with this in mind.
- There was not nearly enough time for the paper as expected, so a complete draft should have been completely finished before the start of the break
    - Extracting results and fixing that program takes 1-2weeks
    - Writing the paper takes 2-3 weeks
    - So next time: Paper of this size should be started 4 weeks in advance and become a full-time priority
    My next research internship will require a paper as well
        - I will write the introduction draft while I am doing my literature study
        - I will start writing the methodology after obtaining and splitting the data
        - It should reflect my research more than it should reflect my results

### Things I did well

- I was able to translate the problem and requested solution to a vision that I was able to continuously communicate with the team
- I took on the role of the Scrum-master and made it possible for other team members who also never used scrum to work within this framework
- I was (after the first few weeks) clear in my notebooks and used the markdown cells extensively to make sure other people could work with my notebooks.