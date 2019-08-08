# Palladio Tutorial

This tutorial was written by <a href="https://www.grinnell.edu/users/waldenka">Katherine Walden</a>, Digital Liberal Arts Specialist at Grinnell College.

This tutorial was reviewed by <a href="https://www.grinnell.edu/users/purcelsj">Sarah Purcell</a> (L.F. Parker Professor of History) and <a href="https://www.grinnell.edu/users/donovang">Gina Donovan</a> (Instructional Technologist) at Grinnell College, and edited by Papa Ampim-Darko, a student research assistant at Grinnell College.

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
Network Analysis-Part I (Palladio) is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

<hr />

As the authors of <em>Exploring Big Historical Data </em>outline in Chapter 7, historians can use a wide range of software programs and digital tools for network analysis and network visualizations. In this tutorial, we will use a combination of Palladio (a web-based GUI interface), NetworkX (a Python package) and Gephi (an GUI software) to explore various aspects of network analysis and visualization.

<hr />

## Network Analysis using Palladio

<em>Developed through a National Endowment for the Humanities Implementation grant, <a href="http://hdlab.stanford.edu/palladio/">Palladio</a> was released by Stanford University in June 2016. Designed for historians and other digital humanities scholars, Palladio is a web-based application that allows users to analyze data that includes time and network features and display that data via maps, timelines, other types of visualizations, and gallery exhibits. Designed as a browser-based GUI interface, Palladio works well for quick visualizations and offers limited interactive export options.</em>

<hr />

## Data

1-We will be working with sample networked data sets based on the <a href="http://www.oxforddnb.com/">Oxford Dictionary of National Biography</a> and the <a href="http://www.sixdegreesoffrancisbacon.com/">Six Degrees of Francis Bacon</a> project. These data sets include a list of names and relationships for early seventeenth-century Quakers.

2-Download the the quakers_nodelist and quakers_edgelist CSV files from this repository 

3-Save the files to your Desktop.

4-Open these files in Microsoft Excel to explore the data structure.

<blockquote>
<ul>
 	<li><em>What types of historical figures are represented? </em></li>
 	<li><em>How are they described in the nodelist data? </em></li>
 	<li><em>What additional questions do you have about the individuals who will be represented as nodes? </em></li>
 	<li><em>How is the edgelist data structured?</em></li>
 	<li><em>Based on a preliminary scan of the nodelist and edgelist CSV data, what types of networks do you think this data might illuminate? </em></li>
 	<li><em>Are there gaps, silences, or alternative networks that are not accounted for in the data?</em></li>
</ul>
</blockquote>

<hr />

## Loading data into Palladio

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_1.PNG?raw=true"><img class="aligncenter size-large wp-image-498" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_1.PNG?raw=true" alt="" width="676" height="334" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_2.PNG?raw=true"><img class="aligncenter size-large wp-image-499" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_2.PNG?raw=true" alt="" width="676" height="454" /></a></p>

5-Open the <a href="http://hdlab.stanford.edu/palladio/">Palladio home page</a> in Chrome or Firefox. Click on the <strong>Start</strong> icon to open a new project.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_3.PNG?raw=true"><img class="aligncenter size-full wp-image-500" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_3.PNG?raw=true" alt="" width="876" height="764" /></a></p>

6-<strong>Drag and drop</strong> the nodelist CSV into the <strong>Load csv</strong> window.

7-Click the <strong>Load</strong> icon to load the data into Palladio.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_4.PNG?raw=true"><img class="aligncenter size-full wp-image-486" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_4.PNG?raw=true" alt="" width="502" height="531" /></a></p>

8-Click on <strong>“Untitled”</strong> to relabel the table as <strong>Node_List</strong> or another descriptive name. You may notice Palladio has a red dot next to the Historical Significance field. <strong>Click on the red dot</strong> to open the <strong>Edit dimension</strong> pop-up window.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_5.PNG?raw=true"><img class="aligncenter size-full wp-image-487" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_5.PNG?raw=true" alt="" width="897" height="636" /></a></p>

9-Palladio requires you to verify special or unexpected characters in the data fields—in this case, a comma in the “maker of clocks, watches, and barometers” role. Click <strong>Verify special characters </strong>icon, then click <strong>Done</strong>.

10-Back on the <strong>Data screen</strong>, you can see the error has been resolved, and Palladio has also automatically described your data fields as a text, date, or number. Before visualizing this data, we want to also load the edgelist data.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_6.PNG?raw=true"><img class="aligncenter size-full wp-image-488" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_6.PNG?raw=true" alt="" width="910" height="636" /></a></p>

11-Click on the <strong>Name field</strong> to open the <strong>Edit dimension</strong> window again.

12-Under <strong>Extension</strong>, click the <strong>Add a new table</strong> icon.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_7.PNG?raw=true"><img class="aligncenter size-full wp-image-489" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_7.PNG?raw=true" alt="" width="903" height="571" /></a></p>

13-<strong>Drag and drop</strong> the <strong>edgelist CSV file</strong> into the <strong>Add new table</strong> area. Click the <strong>Load</strong> icon.

14-Palladio returns to the <strong>Edit dimension</strong> window and tells you out of the 119 names included in the nodelist table, 78 also appear in the edgelist table.

15-Click the <strong>Done</strong> icon to add the new table to your Palladio project.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true"><img class="aligncenter size-large wp-image-490" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_8.PNG?rawtrue" alt="" width="676" height="342" /></a></p>

16-The new <strong>Untitled</strong> table will appear in your <strong>Data</strong> tab. Rename the new table <strong>Edge_List</strong> or another descriptive name. Click on <strong>Provide a title to this project</strong> to rename the project <strong>Network_Tutorial</strong> or another descriptive name.

<hr />

## Analyzing and Visualizing Data in Palladio

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_9.PNG?raw=true"><img class="aligncenter size-full wp-image-491" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_9.PNG?raw=true" alt="" width="391" height="55" /></a></p>

17-Palladio does offer mapping functionality, but our data does not contain spatial information. Click on the <strong>Graph tab</strong> to start building a network visualization.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_10.PNG?raw=true"><img class="aligncenter size-full wp-image-492" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_10.PNG?raw=true" alt="" width="614" height="364" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true"><img class="aligncenter size-large wp-image-493" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true" alt="" width="676" height="314" /></a></p>

18-Select <strong>Source</strong> as the <strong>Source dimension</strong> and <strong>Target</strong> as the <strong>Target dimension</strong>, and Palladio will generate a network graph.

19-What do you notice about the networks generated in Palladio? How would you describe these networks using the terminology outlined in Chapter 6 of <em>Exploring Big Historical Data</em>? What surprises you about the networks, or what additional questions do you have?

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_13.PNG?raw=true"><img class="aligncenter size-large wp-image-495" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_13.PNG?raw=true" alt="" width="676" height="310" /></a></p>

20-Check the bock next to <strong>Size nodes</strong> and select <strong>Number of Edge_List</strong> for <strong>According to</strong>. These changes sized our nodes based on where they appear in the edge_list data. Select <strong>Number of Node_List</strong> for <strong>According to</strong>, and the nodes are sized according to where they appear in the node_list data.

21-How do these graphs differ? What do they highlight or emphasize about the data? What questions do you have?

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_14.PNG?raw=true"><img class="aligncenter size-large wp-image-496" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_14.PNG?raw=true" alt="" width="676" height="301" /></a></p>

22-We can choose other <strong>Source</strong> and <strong>Target</strong> fields to alter the network visualization. For example, choosing <strong>Gender</strong> as <strong>Source</strong> and <strong>Name</strong> as <strong>Target</strong> reveals the gender ratio of the names represented in the data.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_15.PNG?raw=true"><img class="aligncenter size-large wp-image-497" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_15.PNG?raw=true" alt="" width="676" height="306" /></a></p>

23-Choosing <strong>Gender</strong> as <strong>Source</strong> and <strong>Historical Significance</strong> as <strong>Target</strong> highlights the gendering of historical roles in the data set.

24-Palladio offers additional facet, timeline, and timespan analysis via the buttons on the bottom of the page. Feel free to explore these additional functions on your own.
