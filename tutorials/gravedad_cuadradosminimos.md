~~~
<!-- PlutoStaticHTML.Begin -->
<!--
    # This information is used for caching.
    [PlutoStaticHTML.State]
    input_sha = "0897ef58f6fd55dd002dd9047c1931efc0e8d7f360ef3680c84c6ebd2a0dac9e"
    julia_version = "1.7.3"
-->
<pre class='language-julia'><code class='language-julia'>using Plots</code></pre>


<pre class='language-julia'><code class='language-julia'>using PlutoUI, CSV,DataFrames</code></pre>


<pre class='language-julia'><code class='language-julia'># ╔═╡ b19aa6c6-78d0-499f-bc81-344acd9c01f6
plotly()</code></pre>
<pre id='var-hash122875' class='code-output documenter-example-output'>Plots.PlotlyBackend()</pre>


<div class="markdown"><h1>Ajuste de datos</h1>
</div>


<div class="markdown"><h2>Relación entre Fahrenheit y Celsius</h2>
</div>


<div class="markdown"><div class="admonition is-tip">
  <header class="admonition-header">
    💡 Relación
  </header>
  <div class="admonition-body">
    <p>La relacion entre <span class="tex">$°C$</span> y <span class="tex">$°F$</span> sabemos que es &#40;en realidad la googleamos&#41; <span class="tex">$°F&#61;  1.8 °C &#43; 32$</span> </p>
  </div>
</div>
<p>Grafiquemos la relacion tomando 10 puntos</p>
</div>

<pre class='language-julia'><code class='language-julia'>n = 20 # Cantidad de puntos a utilizar</code></pre>
<pre id='var-n' class='code-output documenter-example-output'>20</pre>

<pre class='language-julia'><code class='language-julia'># Acá vamos a tomar 10 valores (n=10) aleatorios entre -10 y 100 y luego los ordenamos de menor a mayor

°C = sort((rand(-10:80,n))) </code></pre>
<pre id='var-°C' class='code-output documenter-example-output'>20-element Vector{Int64}:
 -5
  4
 17
 18
 21
 39
 45
  ⋮
 59
 63
 70
 74
 76
 78</pre>

<pre class='language-julia'><code class='language-julia'>°F = 1.8 .* °C .+ 32</code></pre>
<pre id='var-°F' class='code-output documenter-example-output'>20-element Vector{Float64}:
  23.0
  39.2
  62.6
  64.4
  69.80000000000001
 102.2
 113.0
   ⋮
 138.2
 145.4
 158.0
 165.20000000000002
 168.8
 172.4</pre>

<pre class='language-julia'><code class='language-julia'>begin
    plot(°C,°F, m=:c, mc=:red,legend=false)
    xlabel!("°C")
    ylabel!("°F")

end</code></pre>
<script src="https://cdn.plot.ly/plotly-2.6.3.min.js"></script>    <div id="dac34922-e2c2-46c0-be96-67397bf34c71" style="width:600px;height:400px;"></div>
    <script>
    
        Plotly.newPlot('dac34922-e2c2-46c0-be96-67397bf34c71', [
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            -5.0,
            4.0,
            17.0,
            18.0,
            21.0,
            39.0,
            45.0,
            46.0,
            47.0,
            47.0,
            49.0,
            49.0,
            50.0,
            52.0,
            59.0,
            63.0,
            70.0,
            74.0,
            76.0,
            78.0
        ],
        "showlegend": true,
        "mode": "lines+markers",
        "name": "y1",
        "zmin": null,
        "legendgroup": "y1",
        "marker": {
            "symbol": "circle",
            "color": "rgba(255, 0, 0, 1.000)",
            "line": {
                "color": "rgba(0, 0, 0, 1.000)",
                "width": 1
            },
            "size": 8
        },
        "zmax": null,
        "line": {
            "color": "rgba(0, 154, 250, 1.000)",
            "shape": "linear",
            "dash": "solid",
            "width": 1
        },
        "y": [
            23.0,
            39.2,
            62.6,
            64.4,
            69.80000000000001,
            102.2,
            113.0,
            114.8,
            116.60000000000001,
            116.60000000000001,
            120.2,
            120.2,
            122.0,
            125.60000000000001,
            138.2,
            145.4,
            158.0,
            165.20000000000002,
            168.8,
            172.4
        ],
        "type": "scatter"
    }
]
, {
    "showlegend": false,
    "xaxis": {
        "showticklabels": true,
        "gridwidth": 0.5,
        "tickvals": [
            0.0,
            20.0,
            40.0,
            60.0,
            80.0
        ],
        "range": [
            -7.49,
            80.49
        ],
        "domain": [
            0.07646908719743364,
            0.9934383202099737
        ],
        "mirror": false,
        "tickangle": 0,
        "showline": true,
        "ticktext": [
            "0",
            "20",
            "40",
            "60",
            "80"
        ],
        "zeroline": false,
        "tickfont": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 11
        },
        "zerolinecolor": "rgba(0, 0, 0, 1.000)",
        "anchor": "y",
        "visible": true,
        "ticks": "inside",
        "tickmode": "array",
        "linecolor": "rgba(0, 0, 0, 1.000)",
        "showgrid": true,
        "title": "°C",
        "gridcolor": "rgba(0, 0, 0, 0.100)",
        "titlefont": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 15
        },
        "tickcolor": "rgb(0, 0, 0)",
        "type": "-"
    },
    "paper_bgcolor": "rgba(255, 255, 255, 1.000)",
    "annotations": [],
    "height": 400,
    "margin": {
        "l": 0,
        "b": 20,
        "r": 0,
        "t": 20
    },
    "plot_bgcolor": "rgba(255, 255, 255, 1.000)",
    "yaxis": {
        "showticklabels": true,
        "gridwidth": 0.5,
        "tickvals": [
            30.0,
            60.0,
            90.0,
            120.0,
            150.0
        ],
        "range": [
            18.518,
            176.882
        ],
        "domain": [
            0.07581474190726165,
            0.9901574803149606
        ],
        "mirror": false,
        "tickangle": 0,
        "showline": true,
        "ticktext": [
            "30",
            "60",
            "90",
            "120",
            "150"
        ],
        "zeroline": false,
        "tickfont": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 11
        },
        "zerolinecolor": "rgba(0, 0, 0, 1.000)",
        "anchor": "x",
        "visible": true,
        "ticks": "inside",
        "tickmode": "array",
        "linecolor": "rgba(0, 0, 0, 1.000)",
        "showgrid": true,
        "title": "°F",
        "gridcolor": "rgba(0, 0, 0, 0.100)",
        "titlefont": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 15
        },
        "tickcolor": "rgb(0, 0, 0)",
        "type": "-"
    },
    "width": 600
}
);

    
    </script>



<div class="markdown"><div class="admonition is-info">
  <header class="admonition-header">
    💻 Buscando una relación
  </header>
  <div class="admonition-body">
    <p>Supongamos que tenemos dos termómetros, uno que mide en °C y otro en °F. Tratemos 	de encontrar una relacion entre ambas magnitudes. Nota: Acá vamos a suponer que el primer termómetro es ideal, es decir que no 		tiene errores en la medición</p>
  </div>
</div>
</div>




<pre class='language-julia'><code class='language-julia'>#Generacion de los datos del termómetro que mide en °F
# Vemos que la medida es identica a la que teniamos antes + un ruido
# que generamos y multiplicamos por un número aleatorio
°Fᵣ = °F .+ ruido * rand(n)</code></pre>
<pre id='var-°Fᵣ' class='code-output documenter-example-output'>20-element Vector{Float64}:
  23.0
  39.2
  62.6
  64.4
  69.80000000000001
 102.2
 113.0
   ⋮
 138.2
 145.4
 158.0
 165.20000000000002
 168.8
 172.4</pre>


<div class="markdown"><p>Aplicamos el método de cuadrados mínimos </p>
</div>

<pre class='language-julia'><code class='language-julia'>begin
    Mᵣ = [length(°C)  sum(°C); sum(°C)  sum(°C .^ 2)]
    cᵣ = [sum(°Fᵣ); sum(°C .* °Fᵣ)]
    αsol = Mᵣ \ cᵣ
end</code></pre>
<pre id='var-cᵣ' class='code-output documenter-example-output'>2-element Vector{Float64}:
 32.00000000000004
  1.7999999999999994</pre>


<div class="markdown"><p>ruido &#61; <bond def="ruido" unique_id="vyHXoIy/P1qg"><input type='range' min='1' max='101' value='1'><script>
					const input_el = currentScript.previousElementSibling
					const output_el = currentScript.nextElementSibling
					const displays = ["0.0", "0.5", "1.0", "1.5", "2.0", "2.5", "3.0", "3.5", "4.0", "4.5", "5.0", "5.5", "6.0", "6.5", "7.0", "7.5", "8.0", "8.5", "9.0", "9.5", "10.0", "10.5", "11.0", "11.5", "12.0", "12.5", "13.0", "13.5", "14.0", "14.5", "15.0", "15.5", "16.0", "16.5", "17.0", "17.5", "18.0", "18.5", "19.0", "19.5", "20.0", "20.5", "21.0", "21.5", "22.0", "22.5", "23.0", "23.5", "24.0", "24.5", "25.0", "25.5", "26.0", "26.5", "27.0", "27.5", "28.0", "28.5", "29.0", "29.5", "30.0", "30.5", "31.0", "31.5", "32.0", "32.5", "33.0", "33.5", "34.0", "34.5", "35.0", "35.5", "36.0", "36.5", "37.0", "37.5", "38.0", "38.5", "39.0", "39.5", "40.0", "40.5", "41.0", "41.5", "42.0", "42.5", "43.0", "43.5", "44.0", "44.5", "45.0", "45.5", "46.0", "46.5", "47.0", "47.5", "48.0", "48.5", "49.0", "49.5", "50.0"]
					
					input_el.addEventListener("input", () => {
						output_el.value = displays[input_el.valueAsNumber - 1]
					})
					</script><output style='
						font-family: system-ui;
    					font-size: 15px;
    					margin-left: 3px;
    					transform: translateY(-4px);
    					display: inline-block;'>0.0</output></bond></p>
</div>

<pre class='language-julia'><code class='language-julia'>#ruido = sum(  (mᵉ.*x .+ bᵉ .- y).^2 ) /(n-2)</code></pre>


<pre class='language-julia'><code class='language-julia'>begin

    scatter(°C,°Fᵣ,color=:red,label="datos con ruido")
    for i=1 : length(°C)
        plot!([°C[i],°C[i]], [αsol[2]*°C[i]+αsol[1],°Fᵣ[i]], color=:gray, ls=:dash, label=false)
    end
    plot!(°C, αsol[2].*°C .+ αsol[1],  color=:blue, label="Recta que mejor aproxima")
    plot!(°C,°F,alpha=.5,label="Teoria",color=:green,size=(650, 300))
    
    xlabel!("°C")
    ylabel!("°F")
    plot!(legend=:top)


end</code></pre>
<script src="https://cdn.plot.ly/plotly-2.6.3.min.js"></script>    <div id="ca171e18-138e-4881-8eee-54a82fec39f9" style="width:650px;height:300px;"></div>
    <script>
    
        Plotly.newPlot('ca171e18-138e-4881-8eee-54a82fec39f9', [
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            -5.0,
            4.0,
            17.0,
            18.0,
            21.0,
            39.0,
            45.0,
            46.0,
            47.0,
            47.0,
            49.0,
            49.0,
            50.0,
            52.0,
            59.0,
            63.0,
            70.0,
            74.0,
            76.0,
            78.0
        ],
        "showlegend": true,
        "mode": "markers",
        "name": "datos con ruido",
        "zmin": null,
        "legendgroup": "datos con ruido",
        "marker": {
            "symbol": "circle",
            "color": "rgba(255, 0, 0, 1.000)",
            "line": {
                "color": "rgba(0, 0, 0, 1.000)",
                "width": 1
            },
            "size": 8
        },
        "zmax": null,
        "y": [
            23.0,
            39.2,
            62.6,
            64.4,
            69.80000000000001,
            102.2,
            113.0,
            114.8,
            116.60000000000001,
            116.60000000000001,
            120.2,
            120.2,
            122.0,
            125.60000000000001,
            138.2,
            145.4,
            158.0,
            165.20000000000002,
            168.8,
            172.4
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            -5.0,
            -5.0
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            23.000000000000046,
            23.0
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            4.0,
            4.0
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            39.20000000000004,
            39.2
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            17.0,
            17.0
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            62.60000000000004,
            62.6
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            18.0,
            18.0
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            64.40000000000003,
            64.4
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            21.0,
            21.0
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            69.80000000000004,
            69.80000000000001
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            39.0,
            39.0
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            102.20000000000002,
            102.2
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            45.0,
            45.0
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            113.00000000000001,
            113.0
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            46.0,
            46.0
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            114.80000000000001,
            114.8
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            47.0,
            47.0
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            116.60000000000001,
            116.60000000000001
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            47.0,
            47.0
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            116.60000000000001,
            116.60000000000001
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            49.0,
            49.0
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            120.20000000000002,
            120.2
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            49.0,
            49.0
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            120.20000000000002,
            120.2
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            50.0,
            50.0
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            122.00000000000001,
            122.0
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            52.0,
            52.0
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            125.60000000000001,
            125.60000000000001
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            59.0,
            59.0
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            138.2,
            138.2
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            63.0,
            63.0
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            145.4,
            145.4
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            70.0,
            70.0
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            158.0,
            158.0
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            74.0,
            74.0
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            165.2,
            165.20000000000002
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            76.0,
            76.0
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            168.8,
            168.8
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            78.0,
            78.0
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            172.39999999999998,
            172.4
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            -5.0,
            4.0,
            17.0,
            18.0,
            21.0,
            39.0,
            45.0,
            46.0,
            47.0,
            47.0,
            49.0,
            49.0,
            50.0,
            52.0,
            59.0,
            63.0,
            70.0,
            74.0,
            76.0,
            78.0
        ],
        "showlegend": true,
        "mode": "lines",
        "name": "Recta que mejor aproxima",
        "zmin": null,
        "legendgroup": "Recta que mejor aproxima",
        "zmax": null,
        "line": {
            "color": "rgba(0, 0, 255, 1.000)",
            "shape": "linear",
            "dash": "solid",
            "width": 1
        },
        "y": [
            23.000000000000046,
            39.20000000000004,
            62.60000000000004,
            64.40000000000003,
            69.80000000000004,
            102.20000000000002,
            113.00000000000001,
            114.80000000000001,
            116.60000000000001,
            116.60000000000001,
            120.20000000000002,
            120.20000000000002,
            122.00000000000001,
            125.60000000000001,
            138.2,
            145.4,
            158.0,
            165.2,
            168.8,
            172.39999999999998
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            -5.0,
            4.0,
            17.0,
            18.0,
            21.0,
            39.0,
            45.0,
            46.0,
            47.0,
            47.0,
            49.0,
            49.0,
            50.0,
            52.0,
            59.0,
            63.0,
            70.0,
            74.0,
            76.0,
            78.0
        ],
        "showlegend": true,
        "mode": "lines",
        "name": "Teoria",
        "zmin": null,
        "legendgroup": "Teoria",
        "zmax": null,
        "line": {
            "color": "rgba(0, 128, 0, 0.500)",
            "shape": "linear",
            "dash": "solid",
            "width": 1
        },
        "y": [
            23.0,
            39.2,
            62.6,
            64.4,
            69.80000000000001,
            102.2,
            113.0,
            114.8,
            116.60000000000001,
            116.60000000000001,
            120.2,
            120.2,
            122.0,
            125.60000000000001,
            138.2,
            145.4,
            158.0,
            165.20000000000002,
            168.8,
            172.4
        ],
        "type": "scatter"
    }
]
, {
    "showlegend": true,
    "xaxis": {
        "showticklabels": true,
        "gridwidth": 0.5,
        "tickvals": [
            0.0,
            20.0,
            40.0,
            60.0,
            80.0
        ],
        "range": [
            -7.49,
            80.49
        ],
        "domain": [
            0.07058684972070799,
            0.9939430648092065
        ],
        "mirror": false,
        "tickangle": 0,
        "showline": true,
        "ticktext": [
            "0",
            "20",
            "40",
            "60",
            "80"
        ],
        "zeroline": false,
        "tickfont": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 11
        },
        "zerolinecolor": "rgba(0, 0, 0, 1.000)",
        "anchor": "y",
        "visible": true,
        "ticks": "inside",
        "tickmode": "array",
        "linecolor": "rgba(0, 0, 0, 1.000)",
        "showgrid": true,
        "title": "°C",
        "gridcolor": "rgba(0, 0, 0, 0.100)",
        "titlefont": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 15
        },
        "tickcolor": "rgb(0, 0, 0)",
        "type": "-"
    },
    "paper_bgcolor": "rgba(255, 255, 255, 1.000)",
    "annotations": [],
    "height": 300,
    "margin": {
        "l": 0,
        "b": 20,
        "r": 0,
        "t": 20
    },
    "plot_bgcolor": "rgba(255, 255, 255, 1.000)",
    "yaxis": {
        "showticklabels": true,
        "gridwidth": 0.5,
        "tickvals": [
            30.0,
            60.0,
            90.0,
            120.0,
            150.0
        ],
        "range": [
            18.518,
            176.882
        ],
        "domain": [
            0.10108632254301551,
            0.9868766404199475
        ],
        "mirror": false,
        "tickangle": 0,
        "showline": true,
        "ticktext": [
            "30",
            "60",
            "90",
            "120",
            "150"
        ],
        "zeroline": false,
        "tickfont": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 11
        },
        "zerolinecolor": "rgba(0, 0, 0, 1.000)",
        "anchor": "x",
        "visible": true,
        "ticks": "inside",
        "tickmode": "array",
        "linecolor": "rgba(0, 0, 0, 1.000)",
        "showgrid": true,
        "title": "°F",
        "gridcolor": "rgba(0, 0, 0, 0.100)",
        "titlefont": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 15
        },
        "tickcolor": "rgb(0, 0, 0)",
        "type": "-"
    },
    "legend_position": {
        "yanchor": "top",
        "xanchor": "center",
        "bordercolor": "rgba(0, 0, 0, 1.000)",
        "bgcolor": "rgba(255, 255, 255, 1.000)",
        "borderwidth": 1,
        "tracegroupgap": 0,
        "y": 1.0,
        "font": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 11
        },
        "title": {
            "font": {
                "color": "rgba(0, 0, 0, 1.000)",
                "family": "sans-serif",
                "size": 15
            },
            "text": ""
        },
        "traceorder": "normal",
        "x": 0.55
    },
    "width": 650
}
);

    
    </script>



<div class="markdown"><h3>Determinación de la gravedad mediante cuadrádos mínimos</h3>
</div>


<div class="markdown"><div class="admonition is-tip">
  <header class="admonition-header">
    💡 Esto nos va a venir bien para Física 1
  </header>
  <div class="admonition-body">
    <p>Queremos encontrar la gravedad experimental utilizando un péndulo. De Física del CBC sabemos que el <strong>periodo</strong> es: <span class="tex">$T &#61; 2 \pi \sqrt&#123;\frac&#123;L&#125;&#123;g&#125;&#125;$</span>. No parecería que podamos encontrar una relacion lineal para encontrar la gravedad, no?</p>
<p>Probemos elevanto todo al cuadrado:</p>
  </div>
<p class="tex">$$T^&#123;2&#125; &#61; &#40;2 \pi \sqrt&#123;\frac&#123;L&#125;&#123;g&#125;&#125;&#41;^&#123;2&#125; &#61; \frac &#123;4 \pi^&#123;2&#125; L&#125;&#123;g&#125;$$</p>
<p>Ahora tenemos algo del estilo  <span class="tex">$y&#61; m x$</span> donde</p>
<p class="tex">$$m&#61; \frac &#123;4\pi^&#123;2&#125;&#125;&#123;g&#125;$$</p>
<p class="tex">$$x&#61;L$$</p>
<p>Entonces si encontramos <span class="tex">$m$</span> podemos conocer la gravedad</p>
</div>
</div>


<div class="markdown"><div class="admonition is-info">
  <header class="admonition-header">
    💻 Generacion de datos
  </header>
  <div class="admonition-body">
    <p>Acá vamos a generar datos para utilizar a partir de la ecuación utilizada más arriba &#40;con un poco de ruido&#41;</p>
  </div>
</div>
</div>

<pre class='language-julia'><code class='language-julia'>begin
    
    g = 9.819 
    x = [0.55, 0.6, 0.7,0.75, 0.8]
    T² = x.*(4π^2)/g 
    T²ₑ = T² .+  randn(5) * 0.10 # subindice e indica "experimental"

end</code></pre>
<pre id='var-T²ₑ' class='code-output documenter-example-output'>5-element Vector{Float64}:
 2.0787121842427854
 2.429260745308338
 2.8394235656042883
 3.2400077255716795
 3.099443431655953</pre>


<div class="markdown"><p>Graficamos para ver que fue lo que generamos</p>
</div>

<pre class='language-julia'><code class='language-julia'>begin
    scatter(x,T²ₑ,label="datos",legend=:bottomright)
    xlabel!("l [m]")
    ylabel!("T² [1/s²]")
end</code></pre>
<script src="https://cdn.plot.ly/plotly-2.6.3.min.js"></script>    <div id="e769af45-eb50-4d77-b654-d17a571f1b15" style="width:600px;height:400px;"></div>
    <script>
    
        Plotly.newPlot('e769af45-eb50-4d77-b654-d17a571f1b15', [
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.55,
            0.6,
            0.7,
            0.75,
            0.8
        ],
        "showlegend": true,
        "mode": "markers",
        "name": "datos",
        "zmin": null,
        "legendgroup": "datos",
        "marker": {
            "symbol": "circle",
            "color": "rgba(0, 154, 250, 1.000)",
            "line": {
                "color": "rgba(0, 0, 0, 1.000)",
                "width": 1
            },
            "size": 8
        },
        "zmax": null,
        "y": [
            2.0787121842427854,
            2.429260745308338,
            2.8394235656042883,
            3.2400077255716795,
            3.099443431655953
        ],
        "type": "scatter"
    }
]
, {
    "showlegend": true,
    "xaxis": {
        "showticklabels": true,
        "gridwidth": 0.5,
        "tickvals": [
            0.55,
            0.6000000000000001,
            0.65,
            0.7000000000000001,
            0.75,
            0.8
        ],
        "range": [
            0.5425000000000001,
            0.8075
        ],
        "domain": [
            0.09128390201224845,
            0.9934383202099738
        ],
        "mirror": false,
        "tickangle": 0,
        "showline": true,
        "ticktext": [
            "0.55",
            "0.60",
            "0.65",
            "0.70",
            "0.75",
            "0.80"
        ],
        "zeroline": false,
        "tickfont": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 11
        },
        "zerolinecolor": "rgba(0, 0, 0, 1.000)",
        "anchor": "y",
        "visible": true,
        "ticks": "inside",
        "tickmode": "array",
        "linecolor": "rgba(0, 0, 0, 1.000)",
        "showgrid": true,
        "title": "l [m]",
        "gridcolor": "rgba(0, 0, 0, 0.100)",
        "titlefont": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 15
        },
        "tickcolor": "rgb(0, 0, 0)",
        "type": "-"
    },
    "paper_bgcolor": "rgba(255, 255, 255, 1.000)",
    "annotations": [],
    "height": 400,
    "margin": {
        "l": 0,
        "b": 20,
        "r": 0,
        "t": 20
    },
    "plot_bgcolor": "rgba(255, 255, 255, 1.000)",
    "yaxis": {
        "showticklabels": true,
        "gridwidth": 0.5,
        "tickvals": [
            2.25,
            2.5,
            2.75,
            3.0,
            3.25
        ],
        "range": [
            2.0438733180029187,
            3.274846591811546
        ],
        "domain": [
            0.07581474190726165,
            0.9901574803149606
        ],
        "mirror": false,
        "tickangle": 0,
        "showline": true,
        "ticktext": [
            "2.25",
            "2.50",
            "2.75",
            "3.00",
            "3.25"
        ],
        "zeroline": false,
        "tickfont": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 11
        },
        "zerolinecolor": "rgba(0, 0, 0, 1.000)",
        "anchor": "x",
        "visible": true,
        "ticks": "inside",
        "tickmode": "array",
        "linecolor": "rgba(0, 0, 0, 1.000)",
        "showgrid": true,
        "title": "T² [1/s²]",
        "gridcolor": "rgba(0, 0, 0, 0.100)",
        "titlefont": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 15
        },
        "tickcolor": "rgb(0, 0, 0)",
        "type": "-"
    },
    "legend_position": {
        "yanchor": "bottom",
        "xanchor": "right",
        "bordercolor": "rgba(0, 0, 0, 1.000)",
        "bgcolor": "rgba(255, 255, 255, 1.000)",
        "borderwidth": 1,
        "tracegroupgap": 0,
        "y": 0.07,
        "font": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 11
        },
        "title": {
            "font": {
                "color": "rgba(0, 0, 0, 1.000)",
                "family": "sans-serif",
                "size": 15
            },
            "text": ""
        },
        "traceorder": "normal",
        "x": 1.0
    },
    "width": 600
}
);

    
    </script>



<div class="markdown"><p>Como vimos que la pendiente se relaciona de alguna manera con la gravedad, simplemente tenemos que encontrarla. Pero como hacemos eso?</p>
<p>Previamente encontramos una forma de encontrar una curva que mejor aproxime una serie de datos donde nos quedaba algo de la forma:</p>
<p class="tex">$$y &#61; \beta_0 &#43; \beta_1 x$$</p>
<p>Donde si vemos bien <span class="tex">$\beta_1$</span> es la pendiente que estamos buscando.</p>
<p>Apliquemos entonces lo que sabemos de <strong>cuadrados minimos</strong></p>
</div>

<pre class='language-julia'><code class='language-julia'>begin
    n1=5
    M = [n1 sum(x); sum(x)  sum(x .^ 2)]
    c = [sum(T²ₑ); sum(x .* T²ₑ)]
    
    βsol = M \ c
end</code></pre>
<pre id='var-M' class='code-output documenter-example-output'>2-element Vector{Float64}:
 -0.28228560023774096
  4.440669309874044</pre>

<pre class='language-julia'><code class='language-julia'>begin
    scatter(x, T²ₑ,color=:red,label="datos con ruido")
    for i=1 : length(x)
        plot!([x[i],x[i]], [βsol[2]*x[i]+βsol[1],T²ₑ[i]], color=:gray, ls=:dash, 		label=false)
    end
    plot!(x,βsol[2].*x .+ βsol[1], color=:blue, label="Recta que mejor aproxima")
    plot!(x,T²,label="Teoria",color=:green,size=(550, 300),legend=:bottomright)

    #plot!(x -&gt; βsol[1] + βsol[2] * x, extrema(x)..., c=:red, lw=2)
    xlabel!("l [m]")
    ylabel!("T² [1/s²]")
end</code></pre>
<script src="https://cdn.plot.ly/plotly-2.6.3.min.js"></script>    <div id="ec97861e-e991-493f-a15d-c31d7e323ff2" style="width:550px;height:300px;"></div>
    <script>
    
        Plotly.newPlot('ec97861e-e991-493f-a15d-c31d7e323ff2', [
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.55,
            0.6,
            0.7,
            0.75,
            0.8
        ],
        "showlegend": true,
        "mode": "markers",
        "name": "datos con ruido",
        "zmin": null,
        "legendgroup": "datos con ruido",
        "marker": {
            "symbol": "circle",
            "color": "rgba(255, 0, 0, 1.000)",
            "line": {
                "color": "rgba(0, 0, 0, 1.000)",
                "width": 1
            },
            "size": 8
        },
        "zmax": null,
        "y": [
            2.0787121842427854,
            2.429260745308338,
            2.8394235656042883,
            3.2400077255716795,
            3.099443431655953
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.55,
            0.55
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            2.160082520192984,
            2.0787121842427854
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.6,
            0.6
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            2.382115985686686,
            2.429260745308338
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.7,
            0.7
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            2.8261829166740897,
            2.8394235656042883
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.75,
            0.75
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            3.0482163821677926,
            3.2400077255716795
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.8,
            0.8
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            3.2702498476614945,
            3.099443431655953
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.55,
            0.6,
            0.7,
            0.75,
            0.8
        ],
        "showlegend": true,
        "mode": "lines",
        "name": "Recta que mejor aproxima",
        "zmin": null,
        "legendgroup": "Recta que mejor aproxima",
        "zmax": null,
        "line": {
            "color": "rgba(0, 0, 255, 1.000)",
            "shape": "linear",
            "dash": "solid",
            "width": 1
        },
        "y": [
            2.160082520192984,
            2.382115985686686,
            2.8261829166740897,
            3.0482163821677926,
            3.2702498476614945
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.55,
            0.6,
            0.7,
            0.75,
            0.8
        ],
        "showlegend": true,
        "mode": "lines",
        "name": "Teoria",
        "zmin": null,
        "legendgroup": "Teoria",
        "zmax": null,
        "line": {
            "color": "rgba(0, 128, 0, 1.000)",
            "shape": "linear",
            "dash": "solid",
            "width": 1
        },
        "y": [
            2.2113381894690485,
            2.4123689339662344,
            2.814430422960607,
            3.015461167457793,
            3.2164919119549795
        ],
        "type": "scatter"
    }
]
, {
    "showlegend": true,
    "xaxis": {
        "showticklabels": true,
        "gridwidth": 0.5,
        "tickvals": [
            0.55,
            0.6000000000000001,
            0.65,
            0.7000000000000001,
            0.75,
            0.8
        ],
        "range": [
            0.5425000000000001,
            0.8075
        ],
        "domain": [
            0.09958243855881652,
            0.992841803865426
        ],
        "mirror": false,
        "tickangle": 0,
        "showline": true,
        "ticktext": [
            "0.55",
            "0.60",
            "0.65",
            "0.70",
            "0.75",
            "0.80"
        ],
        "zeroline": false,
        "tickfont": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 11
        },
        "zerolinecolor": "rgba(0, 0, 0, 1.000)",
        "anchor": "y",
        "visible": true,
        "ticks": "inside",
        "tickmode": "array",
        "linecolor": "rgba(0, 0, 0, 1.000)",
        "showgrid": true,
        "title": "l [m]",
        "gridcolor": "rgba(0, 0, 0, 0.100)",
        "titlefont": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 15
        },
        "tickcolor": "rgb(0, 0, 0)",
        "type": "-"
    },
    "paper_bgcolor": "rgba(255, 255, 255, 1.000)",
    "annotations": [],
    "height": 300,
    "margin": {
        "l": 0,
        "b": 20,
        "r": 0,
        "t": 20
    },
    "plot_bgcolor": "rgba(255, 255, 255, 1.000)",
    "yaxis": {
        "showticklabels": true,
        "gridwidth": 0.5,
        "tickvals": [
            2.25,
            2.5,
            2.75,
            3.0,
            3.25
        ],
        "range": [
            2.042966054340224,
            3.3059959775640557
        ],
        "domain": [
            0.10108632254301551,
            0.9868766404199475
        ],
        "mirror": false,
        "tickangle": 0,
        "showline": true,
        "ticktext": [
            "2.25",
            "2.50",
            "2.75",
            "3.00",
            "3.25"
        ],
        "zeroline": false,
        "tickfont": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 11
        },
        "zerolinecolor": "rgba(0, 0, 0, 1.000)",
        "anchor": "x",
        "visible": true,
        "ticks": "inside",
        "tickmode": "array",
        "linecolor": "rgba(0, 0, 0, 1.000)",
        "showgrid": true,
        "title": "T² [1/s²]",
        "gridcolor": "rgba(0, 0, 0, 0.100)",
        "titlefont": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 15
        },
        "tickcolor": "rgb(0, 0, 0)",
        "type": "-"
    },
    "legend_position": {
        "yanchor": "bottom",
        "xanchor": "right",
        "bordercolor": "rgba(0, 0, 0, 1.000)",
        "bgcolor": "rgba(255, 255, 255, 1.000)",
        "borderwidth": 1,
        "tracegroupgap": 0,
        "y": 0.07,
        "font": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 11
        },
        "title": {
            "font": {
                "color": "rgba(0, 0, 0, 1.000)",
                "family": "sans-serif",
                "size": 15
            },
            "text": ""
        },
        "traceorder": "normal",
        "x": 1.0
    },
    "width": 550
}
);

    
    </script>



<div class="markdown"><p>Vamos ahora a resolver el trabajo práctico de física 1 donde se determina la gravedad pero con los datos de 4 grupos</p>
</div>

<pre class='language-julia'><code class='language-julia'>datos_labo = DataFrame(CSV.File("pendulo_simple.csv"));</code></pre>



<div class="markdown"><p>Vemos que forma tiene </p>
</div>

<pre class='language-julia'><code class='language-julia'>datos_labo</code></pre>
<table>
<tr>
<th></th>
<th>Medicion</th>
<th>Longitud</th>
<th>Periodo</th>
<th>Grupo</th>
</tr>
<tr>
<td>1</td>
<td>1</td>
<td>0.55</td>
<td>1.49</td>
<td>1</td>
</tr>
<tr>
<td>2</td>
<td>2</td>
<td>0.6</td>
<td>1.49</td>
<td>1</td>
</tr>
<tr>
<td>3</td>
<td>3</td>
<td>0.7</td>
<td>1.76</td>
<td>1</td>
</tr>
<tr>
<td>4</td>
<td>4</td>
<td>0.75</td>
<td>1.71</td>
<td>1</td>
</tr>
<tr>
<td>5</td>
<td>5</td>
<td>0.8</td>
<td>1.76</td>
<td>1</td>
</tr>
<tr>
<td>6</td>
<td>6</td>
<td>0.5</td>
<td>1.38</td>
<td>2</td>
</tr>
<tr>
<td>7</td>
<td>7</td>
<td>0.76</td>
<td>1.79</td>
<td>2</td>
</tr>
<tr>
<td>8</td>
<td>8</td>
<td>0.8</td>
<td>1.8</td>
<td>2</td>
</tr>
<tr>
<td>9</td>
<td>9</td>
<td>0.9</td>
<td>1.94</td>
<td>2</td>
</tr>
<tr>
<td>10</td>
<td>10</td>
<td>1.0</td>
<td>2.03</td>
<td>2</td>
</tr>
<tr>
<td>...</td>
</tr>
<tr>
<td>22</td>
<td>22</td>
<td>0.9</td>
<td>1.9</td>
<td>4</td>
</tr>
</table>


<pre class='language-julia'><code class='language-julia'>lₗ , Tₗ = datos_labo.Longitud,datos_labo.Periodo</code></pre>
<pre id='var-Tₗ' class='code-output documenter-example-output'>([0.55, 0.6, 0.7, 0.75, 0.8, 0.5, 0.76, 0.8, 0.9, 1.0  …  0.695, 0.795, 1.18, 1.41, 1.15, 0.72, 0.52, 0.74, 0.87, 0.9], [1.49, 1.49, 1.76, 1.71, 1.76, 1.38, 1.79, 1.8, 1.94, 2.03  …  1.67, 1.8, 2.2, 2.34, 2.2, 1.71, 1.42, 1.85, 1.8, 1.9])</pre>

<pre class='language-julia'><code class='language-julia'>T²ₗ = Tₗ.^2</code></pre>
<pre id='var-T²ₗ' class='code-output documenter-example-output'>22-element Vector{Float64}:
 2.2201
 2.2201
 3.0976
 2.9240999999999997
 3.0976
 1.9043999999999996
 3.2041
 ⋮
 4.840000000000001
 2.9240999999999997
 2.0164
 3.4225000000000003
 3.24
 3.61</pre>

<pre class='language-julia'><code class='language-julia'>begin
    scatter(lₗ,T²ₗ,label="datos",legend=:bottomright,size=(560, 400))
    xlabel!("l [m]")
    ylabel!("T² [1/s²]")

end
</code></pre>
<script src="https://cdn.plot.ly/plotly-2.6.3.min.js"></script>    <div id="f98514f3-e80c-40d6-86a3-a7970f0c49cc" style="width:560px;height:400px;"></div>
    <script>
    
        Plotly.newPlot('f98514f3-e80c-40d6-86a3-a7970f0c49cc', [
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.55,
            0.6,
            0.7,
            0.75,
            0.8,
            0.5,
            0.76,
            0.8,
            0.9,
            1.0,
            1.14,
            0.598,
            0.695,
            0.795,
            1.18,
            1.41,
            1.15,
            0.72,
            0.52,
            0.74,
            0.87,
            0.9
        ],
        "showlegend": true,
        "mode": "markers",
        "name": "datos",
        "zmin": null,
        "legendgroup": "datos",
        "marker": {
            "symbol": "circle",
            "color": "rgba(0, 154, 250, 1.000)",
            "line": {
                "color": "rgba(0, 0, 0, 1.000)",
                "width": 1
            },
            "size": 8
        },
        "zmax": null,
        "y": [
            2.2201,
            2.2201,
            3.0976,
            2.9240999999999997,
            3.0976,
            1.9043999999999996,
            3.2041,
            3.24,
            3.7636,
            4.120899999999999,
            4.5796,
            2.4025000000000003,
            2.7889,
            3.24,
            4.840000000000001,
            5.475599999999999,
            4.840000000000001,
            2.9240999999999997,
            2.0164,
            3.4225000000000003,
            3.24,
            3.61
        ],
        "type": "scatter"
    }
]
, {
    "showlegend": true,
    "xaxis": {
        "showticklabels": true,
        "gridwidth": 0.5,
        "tickvals": [
            0.6000000000000001,
            0.8,
            1.0,
            1.2000000000000002,
            1.4000000000000001
        ],
        "range": [
            0.4727,
            1.4373
        ],
        "domain": [
            0.050185133108361445,
            0.9929696287964006
        ],
        "mirror": false,
        "tickangle": 0,
        "showline": true,
        "ticktext": [
            "0.6",
            "0.8",
            "1.0",
            "1.2",
            "1.4"
        ],
        "zeroline": false,
        "tickfont": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 11
        },
        "zerolinecolor": "rgba(0, 0, 0, 1.000)",
        "anchor": "y",
        "visible": true,
        "ticks": "inside",
        "tickmode": "array",
        "linecolor": "rgba(0, 0, 0, 1.000)",
        "showgrid": true,
        "title": "l [m]",
        "gridcolor": "rgba(0, 0, 0, 0.100)",
        "titlefont": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 15
        },
        "tickcolor": "rgb(0, 0, 0)",
        "type": "-"
    },
    "paper_bgcolor": "rgba(255, 255, 255, 1.000)",
    "annotations": [],
    "height": 400,
    "margin": {
        "l": 0,
        "b": 20,
        "r": 0,
        "t": 20
    },
    "plot_bgcolor": "rgba(255, 255, 255, 1.000)",
    "yaxis": {
        "showticklabels": true,
        "gridwidth": 0.5,
        "tickvals": [
            2.0,
            3.0,
            4.0,
            5.0
        ],
        "range": [
            1.7972639999999998,
            5.582735999999999
        ],
        "domain": [
            0.07581474190726165,
            0.9901574803149606
        ],
        "mirror": false,
        "tickangle": 0,
        "showline": true,
        "ticktext": [
            "2",
            "3",
            "4",
            "5"
        ],
        "zeroline": false,
        "tickfont": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 11
        },
        "zerolinecolor": "rgba(0, 0, 0, 1.000)",
        "anchor": "x",
        "visible": true,
        "ticks": "inside",
        "tickmode": "array",
        "linecolor": "rgba(0, 0, 0, 1.000)",
        "showgrid": true,
        "title": "T² [1/s²]",
        "gridcolor": "rgba(0, 0, 0, 0.100)",
        "titlefont": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 15
        },
        "tickcolor": "rgb(0, 0, 0)",
        "type": "-"
    },
    "legend_position": {
        "yanchor": "bottom",
        "xanchor": "right",
        "bordercolor": "rgba(0, 0, 0, 1.000)",
        "bgcolor": "rgba(255, 255, 255, 1.000)",
        "borderwidth": 1,
        "tracegroupgap": 0,
        "y": 0.07,
        "font": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 11
        },
        "title": {
            "font": {
                "color": "rgba(0, 0, 0, 1.000)",
                "family": "sans-serif",
                "size": 15
            },
            "text": ""
        },
        "traceorder": "normal",
        "x": 1.0
    },
    "width": 560
}
);

    
    </script>



<div class="markdown"><p>Nuevamente hacemos el ajuste por cuadrados minimos</p>
</div>

<pre class='language-julia'><code class='language-julia'>begin
    nₗ=length(lₗ)
    Mₗ = [nₗ  sum(lₗ); sum(lₗ)  sum(lₗ .^ 2)]
    cₗ = [sum(T²ₗ); sum(lₗ .* T²ₗ)]
    
    θsol = Mₗ \ cₗ
end</code></pre>
<pre id='var-nₗ' class='code-output documenter-example-output'>2-element Vector{Float64}:
 0.0019085248794306587
 4.0452545885967774</pre>

<pre class='language-julia'><code class='language-julia'>begin
    scatter(lₗ, T²ₗ,color=:red,label="datos con ruido")
    for i=1 : length(lₗ)
        plot!([lₗ[i],lₗ[i]], [θsol[2]*lₗ[i]+θsol[1],T²ₗ[i]], color=:gray, ls=:dash, 		label=false)
    end
    plot!(lₗ,θsol[2].*lₗ .+ θsol[1], color=:blue, label="Recta que mejor aproxima")
    #plot!(lₗ,T²ₗ,label="Teoria",color=:green,size=(550, 300),legend=:bottomright)
    
    
    xlabel!("l [m]")
    ylabel!("T² [1/s²]")
end</code></pre>
<script src="https://cdn.plot.ly/plotly-2.6.3.min.js"></script>    <div id="14ad5bb3-0dd9-4480-83dd-f40b0c9299cf" style="width:600px;height:400px;"></div>
    <script>
    
        Plotly.newPlot('14ad5bb3-0dd9-4480-83dd-f40b0c9299cf', [
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.55,
            0.6,
            0.7,
            0.75,
            0.8,
            0.5,
            0.76,
            0.8,
            0.9,
            1.0,
            1.14,
            0.598,
            0.695,
            0.795,
            1.18,
            1.41,
            1.15,
            0.72,
            0.52,
            0.74,
            0.87,
            0.9
        ],
        "showlegend": true,
        "mode": "markers",
        "name": "datos con ruido",
        "zmin": null,
        "legendgroup": "datos con ruido",
        "marker": {
            "symbol": "circle",
            "color": "rgba(255, 0, 0, 1.000)",
            "line": {
                "color": "rgba(0, 0, 0, 1.000)",
                "width": 1
            },
            "size": 8
        },
        "zmax": null,
        "y": [
            2.2201,
            2.2201,
            3.0976,
            2.9240999999999997,
            3.0976,
            1.9043999999999996,
            3.2041,
            3.24,
            3.7636,
            4.120899999999999,
            4.5796,
            2.4025000000000003,
            2.7889,
            3.24,
            4.840000000000001,
            5.475599999999999,
            4.840000000000001,
            2.9240999999999997,
            2.0164,
            3.4225000000000003,
            3.24,
            3.61
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.55,
            0.55
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            2.2267985486076585,
            2.2201
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.6,
            0.6
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            2.4290612780374974,
            2.2201
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.7,
            0.7
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            2.8335867368971748,
            3.0976
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.75,
            0.75
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            3.035849466327014,
            2.9240999999999997
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.8,
            0.8
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            3.238112195756853,
            3.0976
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.5,
            0.5
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            2.0245358191778196,
            1.9043999999999996
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.76,
            0.76
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            3.076302012212982,
            3.2041
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.8,
            0.8
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            3.238112195756853,
            3.24
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.9,
            0.9
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            3.6426376546165304,
            3.7636
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            1.0,
            1.0
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            4.047163113476208,
            4.120899999999999
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            1.14,
            1.14
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            4.613498755879757,
            4.5796
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.598,
            0.598
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            2.4209707688603035,
            2.4025000000000003
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.695,
            0.695
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            2.813360463954191,
            2.7889
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.795,
            0.795
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            3.217885922813869,
            3.24
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            1.18,
            1.18
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            4.775308939423628,
            4.840000000000001
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            1.41,
            1.41
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            5.705717494800886,
            5.475599999999999
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            1.15,
            1.15
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            4.653951301765725,
            4.840000000000001
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.72,
            0.72
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            2.9144918286691106,
            2.9240999999999997
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.52,
            0.52
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            2.1054409109497554,
            2.0164
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.74,
            0.74
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            2.995396920441046,
            3.4225000000000003
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.87,
            0.87
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            3.5212800169586274,
            3.24
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.9,
            0.9
        ],
        "showlegend": false,
        "mode": "lines",
        "name": "",
        "zmin": null,
        "legendgroup": "",
        "zmax": null,
        "line": {
            "color": "rgba(128, 128, 128, 1.000)",
            "shape": "linear",
            "dash": "dash",
            "width": 1
        },
        "y": [
            3.6426376546165304,
            3.61
        ],
        "type": "scatter"
    },
    {
        "xaxis": "x",
        "colorbar": {
            "title": ""
        },
        "yaxis": "y",
        "x": [
            0.55,
            0.6,
            0.7,
            0.75,
            0.8,
            0.5,
            0.76,
            0.8,
            0.9,
            1.0,
            1.14,
            0.598,
            0.695,
            0.795,
            1.18,
            1.41,
            1.15,
            0.72,
            0.52,
            0.74,
            0.87,
            0.9
        ],
        "showlegend": true,
        "mode": "lines",
        "name": "Recta que mejor aproxima",
        "zmin": null,
        "legendgroup": "Recta que mejor aproxima",
        "zmax": null,
        "line": {
            "color": "rgba(0, 0, 255, 1.000)",
            "shape": "linear",
            "dash": "solid",
            "width": 1
        },
        "y": [
            2.2267985486076585,
            2.4290612780374974,
            2.8335867368971748,
            3.035849466327014,
            3.238112195756853,
            2.0245358191778196,
            3.076302012212982,
            3.238112195756853,
            3.6426376546165304,
            4.047163113476208,
            4.613498755879757,
            2.4209707688603035,
            2.813360463954191,
            3.217885922813869,
            4.775308939423628,
            5.705717494800886,
            4.653951301765725,
            2.9144918286691106,
            2.1054409109497554,
            2.995396920441046,
            3.5212800169586274,
            3.6426376546165304
        ],
        "type": "scatter"
    }
]
, {
    "showlegend": true,
    "xaxis": {
        "showticklabels": true,
        "gridwidth": 0.5,
        "tickvals": [
            0.6000000000000001,
            0.8,
            1.0,
            1.2000000000000002,
            1.4000000000000001
        ],
        "range": [
            0.4727,
            1.4373
        ],
        "domain": [
            0.04683945756780402,
            0.9934383202099739
        ],
        "mirror": false,
        "tickangle": 0,
        "showline": true,
        "ticktext": [
            "0.6",
            "0.8",
            "1.0",
            "1.2",
            "1.4"
        ],
        "zeroline": false,
        "tickfont": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 11
        },
        "zerolinecolor": "rgba(0, 0, 0, 1.000)",
        "anchor": "y",
        "visible": true,
        "ticks": "inside",
        "tickmode": "array",
        "linecolor": "rgba(0, 0, 0, 1.000)",
        "showgrid": true,
        "title": "l [m]",
        "gridcolor": "rgba(0, 0, 0, 0.100)",
        "titlefont": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 15
        },
        "tickcolor": "rgb(0, 0, 0)",
        "type": "-"
    },
    "paper_bgcolor": "rgba(255, 255, 255, 1.000)",
    "annotations": [],
    "height": 400,
    "margin": {
        "l": 0,
        "b": 20,
        "r": 0,
        "t": 20
    },
    "plot_bgcolor": "rgba(255, 255, 255, 1.000)",
    "yaxis": {
        "showticklabels": true,
        "gridwidth": 0.5,
        "tickvals": [
            2.0,
            3.0,
            4.0,
            5.0
        ],
        "range": [
            1.790360475155973,
            5.819757019644913
        ],
        "domain": [
            0.07581474190726165,
            0.9901574803149606
        ],
        "mirror": false,
        "tickangle": 0,
        "showline": true,
        "ticktext": [
            "2",
            "3",
            "4",
            "5"
        ],
        "zeroline": false,
        "tickfont": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 11
        },
        "zerolinecolor": "rgba(0, 0, 0, 1.000)",
        "anchor": "x",
        "visible": true,
        "ticks": "inside",
        "tickmode": "array",
        "linecolor": "rgba(0, 0, 0, 1.000)",
        "showgrid": true,
        "title": "T² [1/s²]",
        "gridcolor": "rgba(0, 0, 0, 0.100)",
        "titlefont": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 15
        },
        "tickcolor": "rgb(0, 0, 0)",
        "type": "-"
    },
    "legend_position": {
        "yanchor": "auto",
        "xanchor": "auto",
        "bordercolor": "rgba(0, 0, 0, 1.000)",
        "bgcolor": "rgba(255, 255, 255, 1.000)",
        "borderwidth": 1,
        "tracegroupgap": 0,
        "y": 1.0,
        "font": {
            "color": "rgba(0, 0, 0, 1.000)",
            "family": "sans-serif",
            "size": 11
        },
        "title": {
            "font": {
                "color": "rgba(0, 0, 0, 1.000)",
                "family": "sans-serif",
                "size": 15
            },
            "text": ""
        },
        "traceorder": "normal",
        "x": 1.0
    },
    "width": 600
}
);

    
    </script>



<div class="markdown"><div class="admonition is-tip">
  <header class="admonition-header">
    🚧 Falta cuantificar la aproximacion
  </header>
  <div class="admonition-body">
    <p>Mencionamos que que buscamos la mejor aproximacion, pero que significa? podemos ponerle 	un valor?</p>
  </div>
</div>
</div>
<div class='manifest-versions'>
<p>Built with Julia 1.7.3 and</p>
CSV 0.10.2<br>
DataFrames 1.3.2<br>
Plots 1.25.8<br>
PlutoUI 0.7.34
</div>

<!-- PlutoStaticHTML.End -->
~~~