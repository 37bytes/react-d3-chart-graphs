## React-d3-chart-graphs
A javascript library for building charts based on d3.js@4.10.0
Allows you to easily build the following graph:

- [Bar Chart](#BarChart)
- [Stacked Bar Chart](#StackedBarChart)
- [Box Plot](#BoxPlot)

<img src="https://user-images.githubusercontent.com/3080207/29460770-d85faf6a-8431-11e7-9204-be7c4a43220e.png">
 
<a name="BarChart"></a>
## Bar Chart
A bar chart or bar graph is a chart or graph that presents grouped data with rectangular bars with lengths proportional 
to the values that they represent. Only vertical bars are supported.

Consists of the following properties:

- [axesProps.padding](#AxesProps)
- data - type: array of object. 

    Fields:
     ```
    {
        title: "title chart",
        value: 7
    }
     ```
- paddingMultiplier - type: Number (from 0 to 1). Default value = 0. Specifies an indent between bars.
- margins - type: object. Set canvas margins.
    Fields (default values):
     ```
        {
            top: 10,
            right: 10,
            bottom: 150,
            left: 80
        }
     ```
- colorScale - type Object. Sets the color of the bar, depending on the value on the y-axis with the help of the function
 d3-interpolate.
    Fields (default values):
     ```
        {
            min: '#B2EBF2'
            max: '#00BCD4',
        }
     ```  
- handleBarClick - The click event is raised when the user clicks on the canvas. If user clicked on bar
argument - item of data and metrics current bar.
    Fields :
    ```
    {
        metrics: {
            left: 548
            top: 129
            width: 52
        },
        title: "title chart",
        value: 7
    }
    ```
    If user click on canvas without bar, argument is `null`

- handleBarHover - The mouseenter and mouseleave events. If user moved mouse in bar, argument - item of data and 
metrics current bar.
    ```
    {
        metrics: {
            left: 548
            top: 129
            width: 52
        },
        title: "title chart",
        value: 7
    }
    ```
    If user mouseleave bar or if user mouseenter on canvas without bar, arguments is `null`
- toggleResize - type Boolean. Forced resizing by the parent, changing the current state to the opposite will resize.

<a name="StackedBarChart"></a>
## Stacked Bar Chart
Bar graphs can also be used for more complex comparisons of data with grouped bar charts and stacked bar charts.
In a grouped bar chart, for each categorical group there are two or more bars.
 
 Consists of the following properties:
 
 - [axesProps.padding](#AxesProps)
 - data - type: array of object. 
 
     Fields:
      ```
     {
        "titleBar": "first bar",
        "key": "uId", //default titleBar
         "values": [
             {
                 "title": "BAR_1",
                 "value": 5
             },
             {
                 "title": "BAR_2",
                 "value": 7
             },
             {
                 "title": "BAR_3",
                 "value": 5
             },
             {
                 "title": "BAR_4",
                 "value": 10
             },
             {
                 "title": "BAR_5",
                 "value": 20
             },
             {
                 "title": "BAR_6",
                 "value": 5
             },
             {
                 "title": "BAR_7",
                 "value": 9
             },
             {
                 "title": "BAR_8",
                 "value": 12
             },
             {
                 "title": "BAR_9",
                 "value": 4
             }
         ]
     }
      ```
- stackColors -type: object. It is map colors to title data.
    Example:
    ```
    stackColors = {
        BAR_1: {
            color: '#607D8B', //bar color
            legend: 'some bar 1', // legend text
        },
        BAR_2: {
            color: '#4CAF50',
            legend: 'some bar 2',
        },
    }
    ```
- paddingMultiplier - type: Number (from 0 to 1). Default value = 0. Specifies an indent between bars.
- margins - type: object. Set canvas margins.
    Fields (default values):
     ```
        {
            top: 10,
            right: 10,
            bottom: 150,
            left: 80
        }
     ```
- handleBarClick - The click event is raised when the user clicks on the canvas. If user clicked on bar
argument - item of data and metrics current bar and titleBar is a title of stack bars.
    Fields :
    ```
    {
        metrics: {
            left: 548
            top: 129
            width: 52
        },
        title: "title chart",
        value: 7,
        titleBar: "first bar"
    }
    ```
    If user click on canvas without bar, argument is `null`

- handleBarHover - The mouseenter and mouseleave events. If user moved mouse in bar, argument - item of data and 
metrics current bar.
    ```
    {
        metrics: {
            left: 548
            top: 129
            width: 52
        },
        title: "title chart",
        value: 7,
        titleBar: "first bar"
    }
    ```
    If user mouseleave bar or if user mouseenter on canvas without bar, arguments is `null`

- toggleResize - type Boolean. Forced resizing by the parent, changing the current state to the opposite will resize.

<a name="BoxPlot"></a>
## Box Plot
Bar graphs is a method for graphically depicting groups of numerical data through their quartiles.
 
 Consists of the following properties:
 
 - [axesProps.padding](#AxesProps)
 - data - type: array of object. 
 
     Fields:
      ```
     {
         title: 'First bar',
         values: {
             min: 7,
             max: 118,
             median: 20,
             quartiles: {
                 min: 15,
                 max: 40,
             },
         },
     }
      ```
- colorScale - type Object. Sets the color of the bar, depending on the value on the y-axis with the help of the function
 d3-interpolate.
    Fields (default values):
     ```
        {
            min: '#B2EBF2'
            max: '#00BCD4',
        }
     ```  
- paddingMultiplier - type: Number (from 0 to 1). Default value = 0. Specifies an indent between bars.
- margins - type: object. Set canvas margins.
    Fields (default values):
     ```
        {
            top: 10,
            right: 10,
            bottom: 150,
            left: 80
        }
     ```
- handleBarClick - The click event is raised when the user clicks on the bar. 
Argument - item of data and metrics current bar.
    Fields :
    ```
    {
        metrics: {
            left: 548
            top: 129
            width: 52
        },
        title: "title chart",
        values: {
             min: 7,
             max: 118,
             median: 20,
             quartiles: {
                 min: 15,
                 max: 40,
             },
             ejection: {
                 min: 2,
                 max: 220,
             }
        },
        titleBar: "first bar"
    }
    ```
- handleEjectionMaxClick | handleEjectionClickMinClick - The click event is raised when the user clicks on the ejection.
 Argument - item of data and metrics current Circle.
  ```
     {
         metrics: {
             left: 548
             top: 129
             width: 5
         },
         title: 'First bar',
         values: {
             min: 7,
             max: 118,
             median: 20,
             quartiles: {
                 min: 15,
                 max: 40,
             },
             ejection: {
                 min: 2,
                 max: 220,
             }
         }
     }
    ```

- handleBarHover - The mouseenter and mouseleave events. If user moved mouse in bar, argument - item of data and 
metrics current bar.
    ```
    {
        metrics: {
            left: 548
            top: 129
            width: 52
        },
        title: 'First bar',
        values: {
            min: 7,
            max: 118,
            median: 20,
            quartiles: {
                min: 15,
                max: 40,
            },
            ejection: {
                min: 2,
                max: 220,
            }
        }
    }
    ```
    If user mouseleave bar or if user mouseenter on canvas without bar, arguments is `null`

- toggleResize - type Boolean. Forced resizing by the parent, changing the current state to the opposite will resize.
 
<a name="AxesProps"></a>
## Axes props

- axesProps.legend.xAxis || yAxis - Text on legend
- axesProps.padding.xAxis || yAxis - If padding is specified, sets the padding to the specified value in pixels and
  returns the axis. Default value = 5px. [d3-axis tickPadding](#https://github.com/d3/d3-axis#axis_tickPadding)
- axesProps.ticksCount.xAxis || yAxis - [d3-axis tickArguments](https://github.com/d3/d3-axis#axis_tickArguments).
  Default value = 4.
- axesProps.tickFormat.xAxis || yAxis - If format is specified, sets the tick format function and returns the axis.
  [d3-axis axis_tickFormat.](https://github.com/d3/d3-axis#axis_tickFormat)

    Example params:

    ```
    axesProps = {
        label: { //Label text on legend
            xAxis: 'Label bottom axis',
            yAxis: 'Label left axis'
        },
        padding: {
            xAxis: 20,
            yAxis: 20
        },
        ticksCount: 6,
        tickFormat: {
            xAxis: function(value) {
                return value + 'mm';
            }
        }
    }
    ```

<a name="Axes"></a>
## Axes

Component for creating chart's axes. Has the following props:

- `orient`
- `scale`
- `translate`
- `tickSize`
- `legend` see [AxesProps.legend](#AxesProps)
- `padding` see [AxesProps.padding](#AxesProps)
- `ticksCount` see [AxesProps.ticksCount](#AxesProps)
- `tickFormat` see [AxesProps.tickFormat](#AxesProps)

<a name="ResponsiveWrapper"></a>
## Responsive Wrapper

Wrapper component that expands to container's width. Forwards `parentWidth` prop to wrapped component.

Example:

```js
import {Component} from 'react';
import {ResponsiveWrapper} from '@hh.ru/react-d3-chart-graphs';

class MyComponent extends Component {
    render() {
        const { parentWidth } = this.props;
        // ...
    }
}

export default ResponsiveWrapper(MyComponent);
```

## Examples and development
    Show /examples/src/Components. This is create-react-app kit. CLI: cd examples && yarn && cd ../ yarn dev


### 0.1.0

* First release
* Add bar chart and stacked bar chart

### 1.0.0

* Changed data props field in Stacked bar chart

### 2.0.0

* Changed data props stackColors in Stacked bar chart (added legend text)

### 2.0.1

* Changed development build, fix uglify.


### 2.1.0

* Add box plot.

### 2.1.1

* Corrected the positioning of the bar in BoxPlot

### 3.0.0

* Export Axes and ResponsiveWrapper, change axesProps.ticksCount format.

### 3.1.1

* Add handleEjectionClickMinClick, handleEjectionMaxClick in BoxPlot

### 3.1.1

Fix boxPlot mousemove
