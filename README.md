# PyViz---Pythonic-Monopoly

In order for my charts to run in the Panel dashboard, any Matplotlib charts had to first be stored in a figure using Pyplot, and then converted into a pane using pn.panel.Matplotlib(figure_here). When defining a function to display the chart, it was important to use plt.close(figure_here) first, and then return the pane =  pn.panel.Matplotlib(figure_here); otherwise, the function would be calling both the figure and the pane, and neither would show in the dashboard.

HvPlot charts have more built-in compatibility with Panel, so it was unnecessary to convert them. For Plotly Express, the charts would run in the dashboard as long as the panel extension 'Plotly' had to be enabled. Finally, for the neighborhood map, a mapbox API key needed to be exported from an .sh file, and then activated using a mapbox token. Then, the map would run successfully as a plotly express chart.

Once the charts were all properly configured into functions, columns and rows could be created using Panel in the format of my choosing. I deliberately chose not to include hvPlots in the same columns/rows together because they seemed to have unintended cross-interactivity. I then compiled the columns/rows into tabs organized by the types of data displayed, and finally, the dashboard could be run using pn.servable().
