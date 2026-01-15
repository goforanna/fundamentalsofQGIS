<img width="815" height="254" alt="Screenshot 2026-01-12 at 5 21 02 PM" src="https://github.com/user-attachments/assets/d4b88981-6bd0-4504-91e9-c6277eeaa0b8" />


This workshop builds on the foundational concepts of cartography to teach you fundamentals of map creation in QGIS. You will analyze and visualize data from New York City's 311 hotline. Using a fundamental mapping workflow, you will find the answer to the question, "In which NYC neighborhoods are the most noise complaints filed?" No mapping experience is necessary.

In this workshop, you will:
 - Become familiar with the user interface of QGIS
 - Explore and set projected coordinate systems
 - Learn to add, organize, and inspect spatial data
 - Create and export a map layout

---

<p align="center">This workshop is estimated to take you 2.5 hours to complete.</p><p align="center"><a href="sections/Lesson1-GettingOriented.md">Get Started</a> →</p>

---

## Lessons

1. [Getting Oriented in QGIS](sections/Lesson1-GettingOriented.md)
2. [Adding and Organizing Data](sections/Lesson2-AddingData.md)
3. [Analyzing Data](sections/Lesson3-AnalyzingData.md)
4. [Visualizing Data](sections/Lesson4-VisualizingData.md)
5. [Making a Map Layout](sections/Lesson5-MakingLayout.md)
   
---

## Before you get started

In order to follow along with this workhop, you will need to download the related data files. You can download the files from the [Data Download Instructions](DataDownload.md) page. 

If you do not have experience or basic knowledge of the following workshops, you may want to look into those before you start with Fundamentals of QGIS:

- [QGIS Installation Guide](QGISInstallInstructions.md) (required) You will need to download and install QGIS onto your computer in order to follow along with this workshop. You can read the installation guide here.
- [Foundations of Mapping](https://github.com/goforanna/mappingfoundations/tree/v2.0) (required) This workshop will teach you the foundational concepts of GIS that are applicable across platforms. 
- [Data Literacies](https://github.com/DHRI-Curriculum/data-literacies) (recommended) In order to have a better understanding of the data formats we handle in this workshop, if you don't already have a foundational understanding of data formats and types, you can start by walking through our Data Literacies workshop.

### Ethical Considerations

Before you start the Foundations of Mapping workshop, we want to remind you of some ethical considerations to take into account when you read through the lessons of this workshop:

Starting from figuring out how to represent a 3D reality on a 2D plane, there are countless subjective decisions that every mapmaker must make, whether they are conscious of it or not. Mapmakers need to decide what data to represent and what to leave out. They also need to decide how to aggregate, categorize, project, combine, and visualize the data. All of these decisions will influence the story that the map tells. Additionally, as a critical tool of Western colonialism and imperialism, maps wield great authority. As mapmakers, it's essential to be conscious of this history not to reproduce harmful power dynamics through mapmaking. Once something is visualized in the form of a map, it is often understood as a Truth representation of reality. Therefore, mapmakers have an important responsibility to be as honest and transparent as possible. Since the 1980's, there have been two emerging disciplines in academia—critical cartography and feminist GIS—that have brought to light many of the harmful applications of mapping. Rather than reject mapping, they have made significant contributions to the field of GIS and mapping, such as counter mapping, sketch mapping, participatory mapping, qualitative GIS and 3D body-mapping. The following readings will introduce you to some of the fundamental insights from critical cartography and feminist GIS that you can integrate into your mapping journey. The reading list also includes modern-day counter mapping projects.

- Harley, J. B. (1989). [Deconstructing the map](https://quod.lib.umich.edu/p/passages/4761530.0003.008/--deconstructing-the-map?rgn=main;view=fulltext). _Cartographica: The international journal for geographic information and geovisualization_, 26(2), 1-20. This is a classic text by Brian Harley – one of the first Foucauldian analyses of mapping.
- Pavlovskaya, M., & Martin, K. S. (2007). [Feminism and geographic information systems: From a missing object to a mapping subject](https://onlinelibrary.wiley.com/doi/full/10.1111/j.1749-8198.2007.00028.x). _Geography Compass_, 1(3), 583-606. This article makes the case for feminist GIS. 
- Pavlovskaya, M. (2002) [Mapping urban change and changing GIS: Other views of economic restructuring](https://www.researchgate.net/publication/240107165_Mapping_Urban_Change_and_Changing_GIS_Other_views_of_economic_restructuring). _Gender, place and culture: A journal of feminist geography_ 9, 281-289. This study demonstrates how GIS can be part of a critical and feminist analysis of economic development. 
- Kwan, M. P. (2008). [From oral histories to visual narratives: Re-presenting the post-September 11 experiences of the Muslim women in the USA](http://meipokwan.org/Paper/SCG_2008.pdf). _Social & Cultural Geography_, 9(6), 653-669. This study by a feminist GIS scholar uses 3D body maps to challenge the 2D limitations of most maps. She also combines interviews and survey data to create the visualizations. 
- [Counter Mapping: Zuni Maps](https://emergencemagazine.org/feature/counter-mapping/). The indigenous Zuni people describe their mapping project and the ways it challenges Western modes of mapping.

### Pre-reading suggestions

Before you start the Introduction to Mapping workshop, you may want to read a couple of our pre-reading suggestions:

- [Finding the Right Tools for Mapping](https://digitalfellows.commons.gc.cuny.edu/2019/06/03/finding-the-right-tools-for-mapping/)
- [Finding Data for Mapping: Tips and Tricks](https://digitalfellows.commons.gc.cuny.edu/2018/11/24/finding-data-for-mapping-tips-and-tricks/)
- [Create A Rich Multimedia Narrative with ESRI Story Maps](https://digitalfellows.commons.gc.cuny.edu/2019/02/12/create-a-rich-multimedia-narrative-with-esri-story-maps/)

### Projects that use these skills

You may also want to check out a couple of projects that use the skills discussed in this workshop:

- [Visualizing NEH Open Data](https://digitalfellows.commons.gc.cuny.edu/2017/04/04/visualizing-neh-open-data/)
- [Mapping Occupation](https://gcdi.commons.gc.cuny.edu/mapping-occupation-the-union-army-and-the-meaning-of-reconstruction/)
- [NYC’s Worst Evictors](https://www.worstevictorsnyc.org/map/)
- [Torn Apart/Separados](http://xpmethod.columbia.edu/torn-apart/volume/2/index)
- [Native Land](https://native-land.ca/)
- [COVID Mapping Projects](https://digitalfellows.commons.gc.cuny.edu/2020/11/02/mapping-the-effects-of-covid-19/)

---

<p align="center"><a href="sections/Lesson1-GettingOriented.md">Get Started</a> →</p>

---

## Acknowledgements

This workshop is the result of a collaborative effort of a team of people, mostly involved presently or in the past, with the Graduate Center's Digital Initiatives. If you want to see statistics for contributions to this workshop, you can do so [here](https://www.github.com/DHRI-Curriculum/mapping/graphs/contributors). This is a list of all the contributors:

- Current Author: Anna Schlenz
- Past contributing authors: [Javier Otero Peña](https://enviropsych.org/students/javier-otero-pena/) and [Olivia Ildefonso](https://oildefon.medium.com/)
- Editor: [Dr. Lisa Rhody](https://github.com/lmrhody)

---

<sub>[Digital Research Institute (DRI) Curriculum](http://purl.org/dc/terms/) by [Graduate Center Digital Initiatives](https://gcdi.commons.gc.cuny.edu/) is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/). Based on a work at <https://github.com/DHRI-Curriculum>. When sharing this material or derivative works, preserve this paragraph, changing only the title of the derivative work, or provide comparable attribution.</sub>

[![Creative Commons License](https://i.creativecommons.org/l/by-sa/4.0/88x31.png)](http://creativecommons.org/licenses/by-sa/4.0/)
