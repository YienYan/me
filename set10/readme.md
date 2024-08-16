TODO: Reflect on what you learned this week and what is still unclear.
I showed my teacher my map this week and he said he could add some interesting things, I didn't understand correctly, I thought giving pictures of plants was considered interesting. This led to the end of the presentation before I realised I had misunderstood. Then I also went online to learn how to draw scatter plots, bar graphs, maps, how to adjust parameters and so on.

But I found that I learnt all this, but I still couldn't write it myself. So I went to chatgpt for help, and then I found that I could read the steps of chatgpt, and when I came across something with erro, I would check it out myself and correct it myself. I feel that this is a kind of progress, but it is still far from the teacher's requirements.

PRESENTATION ENDED I realised clearly what our third major assignment teacher had specifically asked for. The teacher wanted us to analyse the data and then present the stories behind the individual data, but I thought that me identifying pictures of plants counted as an interesting story. I think I just didn't delve into my code on my own, didn't think on my own, and wasn't motivated. (Final week my focus was on my textile assignment, I roughly estimate I spent about 50 hours on this class during final week) resulting in me spending less time on my core course.

At that time in the evening when I saw that the teacher asked me to talk about some interesting stories I was still catching up with my textile homework and didn't think deeply about the teacher's suggestions or ask my classmates about them because I didn't understand them, I really made a big mistake, luckily I could still modify the code after the presentation.

I finished my assignment for textile at 8.15am at 8:30am. Starting to think hard about what fun stories my data could tell, I went to google searching if there are any very famous trees in Melbourne, and realised that no, there aren't any. It was only on 8.15 that I realised how tricky I had chosen my data.

This code focuses on plotting a scatterplot using the Matplotlib library and performing simple statistics and labelling of the data. 

1. **`fig0 = plt.figure(figsize=(10, 6), num=1)`**.
   - Creates a figure object and sets the size of the figure to 10x6 inches.

2. **`fig0_ax1 = fig0.add_subplot(111)`**:
   - Adds a subplot to the graphic object. Here `111` means create a 1x1 grid with the first subplot.

3. **`fig0_ax1_sc1 = fig0_ax1.scatter(tdf[‘Latitude’], tdf[‘Longitude’], c=tdf[‘Diameter Breast Height’], cmap=‘rainbow’, s=1)`**:
   - Draw a scatter plot with `Latitude` (latitude) as the horizontal coordinate and `Longitude` (longitude) as the vertical coordinate. The colour of the points is determined by `Diameter Breast Height`, using the `rainbow` colour map. The `s=1` indicates the size of the point.

4. **`tree_dia_mean = tdf[‘Diameter Breast Height’].mean()`**.
   - Calculates the mean of `Diameter Breast Height`.

5. **`tree_dia_max = tdf[‘Diameter Breast Height’].max()`**: Calculates the maximum of the breast diameter (`Diameter Breast Height`).
   - Calculates the maximum value of the breast height.

6. **`street_max_items = tdf[(tdf[‘Diameter Breast Height’]) == tree_dia_max]`**:
   - Select the row data where the breast height is equal to the maximum value.

7. **`fig0_ax1.scatter(street_max_items[‘Latitude’], street_max_items[‘Longitude’], c=‘red’, marker=‘*’, s=60, label=‘Max Diameter’)`**:
   - Plot the point where the chest diameter is the maximum, mark it with a red star (`marker=‘*’`), a point size of 60, and add the legend label ‘Max Diameter’.

8. **`text_str = f'Mean: {tree_dia_mean:.2f}cm\nMax: {tree_dia_max:.2f}cm'`**.
   - Creates a string that displays the mean and maximum values with two decimal places.

9. ** `props = dict(boxstyle=‘round’, facecolor=‘wheat’, alpha=0.5)`**:
   - Defines the style of the text box, with `boxstyle` set to rounded rectangle, background colour to light yellow (`wheat`) and alpha to 0.5.

10. **`fig0_ax1.text(0.78, 1.1, text_str, transform=fig0_ax1.transAxes, fontsize=12, verticalalignment=‘top’, bbox=props)`**:
    - Adds text to a specific location on the graph (0.78, 1.1), displaying the mean and maximum values and using the textbox style defined earlier.

11. **`fig0_ax1.set_title(‘All Tree Diameter’)`**:
    - Sets the title of the chart to ‘All Tree Diameter’.

12. **`fig0_ax1.set_xlabel(‘Latitude’)`**: Sets the label for the horizontal coordinate to ‘All Tree Diameter’.
    - Set the label for the horizontal coordinate to ‘Latitude’.

13. **`fig0_ax1.set_ylabel(‘Longitude’)`**: Sets the label for the vertical coordinate to ‘Latitude’.
    - Set the label of the vertical coordinate to ‘Longitude’. 14. **`fig0_ax1.set_ylabel(‘Longitude’)`**.

14. **`fig0_ax1.legend()`**:
    - Adds a legend to display the label ‘Max Diameter’. 15. **`fig0_ax1.legend()`**: Sets the label for the vertical coordinate to ‘Longitude’.

15. **`fig0.colourbar(fig0_ax1_sc1, ax=fig0_ax1)`**: Adds a colour bar to show different chests.
    - Adds a colour bar to show the colour correspondence of different chest diameters.

16. **`location_type = tdf[‘Located in’].unique()`**:
    - Gets the unique value in the `‘Located in’` column, typically used to display all the different location information.

17. **`print(location_type)`**:
    - Prints the different location types.


value_counts(): count the number of occurrences of each com id.
plt.bar() or sns.countplot(): used to plot a bar chart to show the distribution of com ids.
rotation=90: if there are more com ids, the x-axis labels may overlap, so you can rotate them by 90 degrees for better display.

peppercorn_tree_df = df[df[‘common name’] == ‘Peppercorn Tree’].
Filter out the rows with common name ‘Peppercorn Tree’ to get a subset containing only Peppercorn Tree.
plt.scatter():
Show the geographic distribution of Peppercorn Tree using a scatterplot with Latitude as the horizontal coordinate and Longitude as the vertical coordinate.
c=‘green’ sets the scatter colour to green and s=10 sets the scatter size to 10.
plt.xlabel() and plt.ylabel().
Set the labels for the X and Y axes to latitude and longitude, respectively.
plt.title().
Sets the title of the chart to ‘Distribution of Peppercorn Tree’.
plt.legend().
Adds a legend that identifies the data points in the chart as representing the Peppercorn Tree.
plt.show():
Displays the plotted scatterplot.

If you find problems with the Latitude and Longitude columns, you can try converting from Easting and Northing to get latitude and longitude, or extracting valid data from the geolocation column.
If the Latitude and Longitude data is OK, you can try narrowing it down to get a better view of the distribution, or checking to see if there are any outliers that are causing the data points not to be displayed.

mpimg.imread().
This function reads an image file and returns a NumPy array.
plt.imshow().
Uses Matplotlib's imshow() function to display an image in a graph.
plt.axis(‘off’).
Turns off the image's axes so that the image is displayed more clearly and without the distraction of the axes.
plt.show():
Show the image.

plt.xticks(rotation=45, ha=‘right’).
rotation=45: Rotate the labels on the X-axis by 45 degrees.
ha=‘right’: set the label alignment to right to avoid the labels overlapping the columns after rotation.

Change the rotation angle as needed. For example, rotation=90 will display the label vertically.
The ha parameter can be set to ‘centre’, ‘right’ or ‘left’, depending on the effect you want.

Calculate the global mean, maximum and minimum values:.
global_mean = family_mean_diameter.mean(): calculates the global mean of the mean chest diameter of all Families.
global_max = family_mean_diameter.max(): calculates the maximum value of the mean chest diameter for all Families.
global_min = family_mean_diameter.min(): calculates the minimum value of the mean chest diameter for all Families.
Drawing horizontal lines: axhline
axhline is used to draw horizontal lines:
global_mean The mean value is shown by the green dashed line.
global_max shows the maximum value with a solid red line.
global_min shows the minimum value as a solid blue line.
plt.xticks(rotation=45, ha=‘right’).
Rotate the x-axis labels to make sure they don't overlap.

sort_values(ascending=False).
Sort family_mean_diameter in descending order (ascending=False) to sort the mean breast diameter values from highest to lowest.
head(3).
The head(3) function is used to extract the names and mean values of the first three Families after sorting.
tail(3).
The tail(3) function is used to extract the names and averages of the last three Families after sorting.
print().
Outputs the names of the top three and bottom three Families in terms of average chest diameter and their corresponding averages.
top_3_families will contain the three Families with the highest average chest diameter.
bottom_3_families will contain the three Families with the lowest average chest diameter.

for bar in bars:: Iterate over each bar (column).
y_val = bar.get_height(): get the height of the current bar (i.e. the corresponding value).
plt.text(): add text annotation to the top of each bar:
bar.get_x() + bar.get_width() / 2: set the x-axis position of the text to the centre of the bar.
y_val: set the y-axis position of the text to the top of the bar.
f‘{y_val:.2f}’: format the value, keep two decimal places.
ha=‘centre’ and va=‘bottom’: set the horizontal and vertical alignment to centre-aligned and bottom-aligned, respectively, so that the text sits on top of the column.

Use groupby(‘Age Description’) to group the data by Age Description and then calculate the average chest diameter value for each group.
Plot a bar graph:
Use plot(kind=‘bar’, colour=‘lightgreen’) to draw a histogram, with the X-axis representing Age Description and the Y-axis representing mean chest diameter.

Calculate the mean chest diameter by grouping by Useful Life Expectancy:
Use groupby(‘Useful Life Expectency’) to group the data by Useful Life Expectancy and then calculate the mean chest diameter value for each group.

Calculate the mean chest diameter by grouping by Useful Life Expectancy Value:
Use groupby(‘Useful Life Expectancy Value’) to group the data by Useful Life Expectancy Value and then calculate the mean chest diameter value for each group.

