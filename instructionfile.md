# ISQ Instruction File
Guide to replicate the quantitative analyses of the article "Positioning among International Organizations: Shifting Centers of Gravity in Global Health Governance".

## Network analysis

Network analysis consists of a network of IOs and self-declared practices involving another IO. This information can be found in the document **Data3.csv**, where "Source" is the IO declaring the practice, "Year" the year of the report, "Target" the IO concerned by the declaration and "Weight" the number of times this practice takes place in the reporting year. 
This CSV file can be imported into Gephi, an open source network visualization program, specifying that it is the Edges File. 

For practices to appear in the network (and not just IOs), however, it is necessary to create an identifier for each of the lines in this file, as in **Data4.csv**. In the latter, we find a list of relationships between an IO (Source) and a practice (Target) whose identifier aggregates the names of the IOs it connects. This CSV is the source of *Figures 1 and 2*.

To simplify replication and subsequent analysis, we also provide this network data in GEXF (**network.gexf**), a file that can be immediately opened by software such as Gephi. In this file, which is exactly the same as *Figure 1*, it is easy to filter relationships by date to obtain the 5-year intervals shown in *Figure 2*.

## In/Out reporting

The **Data5.xlsx** file aggregates all the lines in the Data3.csv file at IO level and for two-year periods. The visualizations in *Figure 3* were produced directly in Excel. 

## Sankey diagram

The **Data6.csv** file is used to produce *Figure 4*, which aggregates practices at the IO level but retains the details of their classification. The latter information comes from the data produced for the previous paper, which focused on practice categories. Once again, therefore, this is a bipartite edge file (IOs and practice categories), which can be visualized with Gephi or, as in the case of *Figure 2*, with a Sankey-producing tool (e.g. http://sankey-diagram-generator.acquireprocure.com/).
