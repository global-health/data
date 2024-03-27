# ISQ Instruction File
Guide to replicate the quantitative analyses of the article "Positioning among International Organizations: Shifting Centers of Gravity in Global Health Governance".

## Figure 1: Network Analysis

Network analysis consists of a network of IOs and self-declared practices involving another IO. This information can be found in the document **Data3.csv**, where "Source" is the IO declaring the practice, "Year" the year of the report, "Target" the IO concerned by the declaration and "Weight" the number of times this practice takes place in the reporting year. 
This CSV file can be imported into Gephi, an open source network visualization program ([gephi.org](https://gephi.org/)), specifying that it is the Edges File. 

For practices to appear in the network (and not just IOs), however, it is necessary to create an identifier for each of the lines in this file, as in **Data4.csv**. In the latter, we find a list of relationships between an IO (Source) and a practice (Target) whose identifier aggregates the names of the IOs it connects. This CSV is the source of *Figures 1 and 2*.

### Option 1: produce this network on the basis of the CSV file<p align="right">
#### [▶︎ VIDEO GUIDE HERE (option 1)](https://www.youtube.com/watch?v=hN-D809_h14&ab_channel=MartinGrandjean) 

Download **Data4.csv**. Open Gephi and create a new project. In the *Data Laboratory*, click on *Import spreadsheet* and select **Data4.csv**. Make sure the software understand that this is an Edges table and import it in the current workspace (*append to existing workspace*). Go to the *Overview* interface, where the *Context* panel shows that you now have 1027 nodes and 2038 edges. In the *Statistics* panel, run the *Avg. Weighted Degree* metric, then use this metric in the *Appearance* panel to change the size of the nodes (click on "nodes", then "size" - the triple circle logo -, then "ranking", then select "Weighted degree" in the drop-down menu): 5-100 for Min/Max size, then click *Apply*. Then, go to the *Layout* panel and chose "ForceAtlas 2" in the drop-down menu: change the *Scaling* to 50 and check *Prevent Overlap*, then click on *Run*. 
With these settings, you have a perfectly legible network. To obtain a result similar to figure 1, you then need to work on the details. For example, to display the node names, duplicate the *ID* column in the *Label* column in the *Data Laboratory* Nodes table. Or by giving different colours to the IOs to distinguish them from the practices (this can be done manually, since there are few of them and they are the most connected nodes, or by adding an attribute to these nodes in the node table, or by automatically detecting the bipartition of the graph with a plugin like *Multimode Network Transformation*).

<img src="https://raw.githubusercontent.com/global-health/data/master/pictures/screenshot1.png" width="500"/>

### Option 2: simply open the Gephi file provided
#### [▶︎ VIDEO GUIDE HERE (option 2)](https://www.youtube.com/watch?v=2rciBiHURkU&ab_channel=MartinGrandjean) 

To simplify replication and subsequent analysis, we also provide this network data in GEXF (**network.gexf**), a file that can be immediately opened by software such as Gephi. In Gephi, simply go to *File*/*Open* and select the GEXF file. Then, click on the black *T* at the bottom of the *Overview* panel to display the names of the IOs. By checking the *Context* panel, you see that 1027 nodes and 2038 edges is exactly the result of the procedure described in **Option 1**. 

## Figure 2: Network Analysis (filtered)
#### [▶︎ VIDEO GUIDE HERE (filtering)](https://www.youtube.com/watch?v=XiCePq5p4Og&ab_channel=MartinGrandjean) 

*Figure 2* simply consists of versions of *Figure 1* filtered by date to give 5-year intervals. Simply open **network.gexf** as described above and head to the *filters* panel on the right side of the *Overview* interface. Double click on *Attributes*, then on *Range*, then on *year Integer (Edge)*. This opens a little *Range (year) Settings* selection tool at the bottom where you can move the slider to cover 1970-1974 for the first interval (and then click *Filter*), or 1975-1979, 1980-1984, etc. This will remove all the edges that are not occurring during the selected period. This does not remove all the nodes that are not connected anymore (practices that occurs during another period), you can easily remove them by running a new *Avg. Weighted Degree* calculation in the *Statistics* panel and then filter the Nodes table in the *Data Laboratory* according to this attribute and delete all the nodes that scores 0. Removing nodes is not recommended if you still want to experiment with these filters (it is recommended to save the Gephi project before this step, to be able to repeat the operation). Also note that you'll need to recalculate the size of the nodes based on the filtered situation, and that the edges will also be automatically resized when exporting the SVG in the *Preview* interface.

<img src="https://raw.githubusercontent.com/global-health/data/master/pictures/screenshot2.png" width="500"/>

## Figure 3: In/Out Reporting

The **Data5.xlsx** file aggregates all the lines in the Data3.csv file at IO level and for two-year periods. The visualizations in *Figure 3* were produced directly in Microsoft Excel. Just take the 2 columns of a specific IO and create a line or surface chart.

<img src="https://raw.githubusercontent.com/global-health/data/master/pictures/screenshot3.png" width="500"/>

## Figure 4: Sankey Diagram
#### [▶︎ VIDEO GUIDE HERE (sankey)](https://www.youtube.com/watch?v=hN-D809_h14&ab_channel=MartinGrandjean) 

The **Data6.csv** file is used to produce *Figure 4*, which aggregates practices at the IO level but retains the details of their classification. The latter information comes from the data produced for a previous paper ([Bahr et al. 2021](https://brill.com/view/journals/gg/27/1/article-p71_4.xml)), which focused on practice categories. You can access the raw data about the practices in **Data1.csv** and **Data2.csv**, but we prepared **Data6.csv** in a way that makes it easier to visualise as a Sankey diagram, including the IOs.
Once again, therefore, this is a bipartite edge file (IOs and practice categories), which can be visualized with Gephi or, as in the case of *Figure 4*, with an online Sankey-producing tool. Go to [sankey-diagram-generator.acquireprocure.com](http://sankey-diagram-generator.acquireprocure.com/) and click on *Load* -> *Your own data* on the top left of the interface. Then select *CSV* and copy-paste the content of **Data6.csv** in the field and click *Build Sankey*. You now have an interactive but rather raw version of *Figure 4*, that was then exported in SVG and edited in Inkscape to match the colors of the previous figures. Note that the bubbles in the center (meant to show that these categories also have sub-categories) have been added directly in Inkscape and are exactly the bubbles displayed in the figures of our 2021 paper. 

<img src="https://raw.githubusercontent.com/global-health/data/master/pictures/screenshot4.png" width="500"/>
