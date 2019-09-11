
# PEMEX Budget flow visualization 

At Sunday, September 8th, the Mexican Ministry of Finance published the 2020 Government Budget Proposal. For the energy industry, the resources marked for PEMEX (the National Oil Company) were amongst the most important information. This notebook presents a Sankey Diagram that helps to easliy visualize the flow and magnitude of the economic resources proposed for PEMEX in 2020. 

When you hover above the traces, the specific amounts attached to each flow are given as well as the source and target concept. 


```python
# Sankey Diagram Creation

{
    "tags": [
        "hide_input",
    ]
}

import pandas as pd # Load and manage data
import plotly.graph_objects as go # Plot interactive Sankey Diagram
nodes_labels = pd.read_excel('labels-sankey.xlsx')
traces = pd.read_csv('sources-targets-sankey.csv')
nodes_labels = list(nodes_labels['labels'])
sources = list(traces['sources'])
targets = list(traces['targets'])
values = list(traces['values'])
#Construir Sankey
fig = go.Figure(data=[go.Sankey(
    valueformat = "$.2f",
    domain = dict(
        x = [0,1]
    ),
    orientation = 'h',
    node = dict(
      pad = 30,
      thickness = 5,
      line = dict(color = "gray",
                  width = 0.5),
      label = nodes_labels
    ),
    link = dict(
      source = sources,
      target = targets,
      value = values
  ),
    textfont = dict(
        family = 'verdana',
        size = 11
    ),
    arrangement = 'snap',
)])

fig.update_layout(title_text="Destino del presupuesto de PEMEX<br>Flujo: Presupuesto a Actividad Institucional y Programa Presupuestario<br>Unidades: Miles de millones de pesos<br>Fuente: elaboración propia con información de SHCP",
                  font=dict(size = 11, color = '#17202A'),
                  width = 1024, height = 800
                 )
fig.show()
```


<div>
        
        
            <div id="770a6a0c-7bb5-4540-86c1-c06b869b9809" class="plotly-graph-div" style="height:800px; width:1024px;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};
                    
                if (document.getElementById("770a6a0c-7bb5-4540-86c1-c06b869b9809")) {
                    Plotly.newPlot(
                        '770a6a0c-7bb5-4540-86c1-c06b869b9809',
                        [{"arrangement": "snap", "domain": {"x": [0, 1]}, "link": {"source": [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 1, 1, 2, 2, 2, 2, 2, 2, 3, 3, 3, 4, 4, 5, 6, 6, 6, 7, 8, 8, 9, 9, 9, 9, 9, 9, 10, 11, 11, 11], "target": [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 13, 14, 17, 18, 13, 19, 18, 20, 18, 21, 22, 13, 23, 24, 17, 25, 26, 13, 14, 27, 17, 18, 28, 13, 14, 29], "value": [1.38, 42.47, 1.5699999999999998, 50.42, 0.79, 135.29999999999998, 63.89, 12.61, 325.42, 1.37, 1.94, 0.75, 0.56, 0.07, 0.26, 33.55, 1.88, 0.04, 0.06, 6.68, 0.03, 0.96, 0.58, 0.78, 49.64, 0.79, 13.17, 0.17, 121.96, 63.89, 0.17, 12.44, 41.26, 16.0, 0.05, 55.34, 0.64, 212.13, 1.37, 1.12, 0.49, 0.33]}, "node": {"label": ["Presupuesto Total", "Comercializaci\u00f3n", "Distribuci\u00f3n", "Entorno ecol\u00f3gico", "Exploraci\u00f3n de hidrocarburos", "Funci\u00f3n p\u00fablica y buen gobierno", "Gesti\u00f3n de subsidiarias", "Pensiones y jubilaciones", "Personal activo y jubilado saludable y con calidad de vida", "Producci\u00f3n y mantenimiento de instalaciones.", "Servicios de telecomunicaciones", "Servicios relacionadas a pozos", "Comercializaci\u00f3n", "Mantenimiento de infraestructura", "Otros proyectos de infraestructura", "Conservaci\u00f3n de infraestructura mar\u00edtimo-portuaria", "Distribuci\u00f3n", "Programas de adquisiciones", "Proyectos de infraestructura econ\u00f3mica de hidrocarburos", "Operaci\u00f3n y mantenimiento de la infraestructura en ecolog\u00eda", "Estudios de preinversi\u00f3n", "Actividades de apoyo a la funci\u00f3n p\u00fablica y buen gobierno", "Actividades de apoyo administrativo", "Prestaci\u00f3n de servicios corporativos", "Aportaciones para pensiones y jubilaciones", "Servicios m\u00e9dicos", "Compra de acciones o inversiones diversas", "Producci\u00f3n", "Servicios de telecomunicaciones internos ", "Servicios relacionados a pozos"], "line": {"color": "gray", "width": 0.5}, "pad": 30, "thickness": 5}, "orientation": "h", "textfont": {"family": "verdana", "size": 11}, "type": "sankey", "valueformat": "$.2f"}],
                        {"font": {"color": "#17202A", "size": 11}, "height": 800, "template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "zerolinecolor": "white", "zerolinewidth": 2}}}, "title": {"text": "Destino del presupuesto de PEMEX<br>Flujo: Presupuesto a Actividad Institucional y Programa Presupuestario<br>Unidades: Miles de millones de pesos<br>Fuente: elaboraci\u00f3n propia con informaci\u00f3n de SHCP"}, "width": 1024},
                        {"responsive": true}
                    ).then(function(){
                            
var gd = document.getElementById('770a6a0c-7bb5-4540-86c1-c06b869b9809');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>



```python

```
