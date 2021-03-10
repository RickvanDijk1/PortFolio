# Career

## Pieters Bouwtechniek
_sep 2020 - now_

In September 2020 I joined Pieters Bouwtechniek as a Junior Modeller with the intention to explore the company and grow into the role of BIM manager. I worked at projects such as de Nieuwe Hallen, The Hague, the headquarters of an office in Rotterdam and the existing museum Boijmans van Beuningen, Rotterdam. In these and many other projects, I learned the ins and outs of BIM modeling and I learned a lot about structural engineering. Reinforcing concrete in entire projects, researching old archives, and structurally checking the architect's choices in the early stages of the design, were my daily activities. 

![References](https://github.com/RickvanDijk1/PortFolio/blob/gh-pages/assets/img/Examples.png?raw=true "Project examples")
[Larger image](https://github.com/RickvanDijk1/PortFolio/blob/gh-pages/assets/img/Examples.png)

After growing familiar with Revit I started to dive into Dynamo. I feel that Dynamo has great potential because it combines computational power with the most used BIM software. In our office, I saw many possibilities where I could optimize the workflow by implementing Dynamo. At my first large project (HQ of an office, Rotterdam) I started to map out actions that I would repeatedly do and replace them with small Dynamo scripts. These were very simple scripts that would allow me to rotate multiple objects, automatically make hollow-core slabs, tag all the elements in a sheet, or automatically fix foundation poles. 

![Dynamo examples](https://github.com/RickvanDijk1/PortFolio/blob/gh-pages/assets/img/Portfolio_Dynamo.gif?raw=true "Dynamo examples")
[Larger image](https://github.com/RickvanDijk1/PortFolio/blob/gh-pages/assets/img/Portfolio_Dynamo.gif)

I also found out that we spend a lot of time controlling the project and fixing small errors. I started a workflow in Dynamo that would control the project in many ways. It would check all the beams and columns if their name would correspond with their section if columns are attached to another beam, or check if offsets and levels are identical in identical elements. A list of suggested fixes was shown as output and those could automatically be fixed. Until today, this is still a WIP as I am still working on it on the side while working on projects.

In December 2020 I started chatting with a colleague who was working on balconies in ultra-high-strength concrete and she asked if I could help with some workflow optimizations. These projects often have several hundred different balconies, and each type needs its drawings, schedules, and sheets. Prior, each element was individually modeled, dimensioned, and exported. I created scripts that would automatically make views and part lists and place them on a sheet. Also, it would fill in as much information as possible, saving their department a lot of time for each project. I also experimented with the standardisation of dimensioning, as all the elements have identical family types in the views. The script I made, used 1 reference dimension to get the outlines of the family and set the plane to which we wanted to reference the perpendicular planes. I set up a standard script that could be used and edited when a new project has specific demands for the dimensions. 

![Python examples](https://github.com/RickvanDijk1/PortFolio/blob/gh-pages/assets/img/Portfolio_Python.gif?raw=true "Python examples")
[Larger image](https://github.com/RickvanDijk1/PortFolio/blob/gh-pages/assets/img/Portfolio_Python.gif)

In February of 2021 I started to assist a graduate student at our firm and help in her project. Her research is towards the previously described balconies and in finding a standardized shape that can be parametrized. In the research, she opts to create a family that can be edited in Dynamo to create the concrete slab and then adding premade elements (anchors, openings and gains) to it in Dynamo as well. 

## Alklima Warmtepompen
_Oct 2017 - Apr 2019_

During my bachelors I wanted to acquire experience at an office in the built environment. I found a job near my hometown where I assisted the sales department of a distributor of heat-pumps. My activities were to make cooling/heating calculations, design heat-pump systems and answer questions that many installers had. I worked at hotels, schools, single houses and offices. Also during my job, I helped in cleaning up customer databases and databases containing specifications of the heat-pumps. As these databases were based on Excel, I gained proficiency with Excel and macros which I used to automate the process. 
