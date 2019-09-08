---
title: Overview
description: Learn about the building blocks that Mapbox provides so you can create custom mapping applications.
headerImage: /help/img/categories/guide.svg
color: cyan
prependJs:
  - "import constants from '../../constants.json';"
  - "import ChevronousText from '@mapbox/mr-ui/chevronous-text';"
  - "import DemoIframe from '@mapbox/dr-ui/demo-iframe';"
  - "import { DemoStatic } from '../../components/demo-static';"
  - "import { HmwMapSources } from '../../components/diagrams/hmw-map-sources';"
  - "import GLWrapper from '@mapbox/dr-ui/gl-wrapper';"
contentType: guide
contentTypeTitle: How Mapbox works
---


---
标题:概览
描述:了解Mapbox提供的构建模块，以创建自定义地图应用.
标题图片:/help/img/categories/guide.svg.\
颜色:青色
前置JS文件:
  - "引入数据从 '../../constants.json';"
  - "引入文本样式从 '@mapbox/mr-ui/chevronous-text';"
  - "引入演示框架从 '@mapbox/dr-ui/demo-iframe';"
  - "引入{ 演示静态文件 } 从 '../../components/demo-static';"
  - "引入{ HMW地图资源 } 从 '../../components/diagrams/hmw-map-sources';"
  - "引入GL封装文件从 '@mapbox/dr-ui/gl-wrapper';"
内容类型：教程指南
内容类型标题：如何使用Mapbox进行工作开发
---


Welcome to Mapbox! Mapbox is a developer platform used [across industries](https://www.mapbox.com/industries) to create custom applications that solve problems with maps, data, and spatial analysis. Mapbox's tools are building blocks that support every part of the web and mobile map-making process. Whether your goal is to build a beautiful map to match your website or to build a full-featured geoprocessing application, we have you covered.

These guides will introduce you to the building blocks of Mapbox and how you can:

- Work with in Mapbox's **robust data**.
- **Style** your map down to the smallest details.
- **Upload** or **create** custom data.
- **Develop** full-featured web and mobile applications.
- **Extend** your app's functionality with web services for [geocoding](/help/glossary/geocoding/), directions, spatial analysis, and more.

欢迎来到Mapbox！MapBox是一个跨行业的开发平台，用于创建自定义应用程序，解决地图、数据和空间分析问题。Mapbox的工具是构建模块，支持Web和移动地图开发制作过程的每个部分。无论您的目标是创建一个精美的地图来匹配您的网站，还是建立一个功能齐全的地理处理应用程序，我们为您提供帮助。

这些指南将向您介绍MapBox的构建以及如何使用：

- 使用MapBox的**大量数据数据**。
- 将你的**地图样式渲染**要素最小细节。
- **上传**或**创建**自定义数据。
- **开发**功能完备的网络和移动地图应用。
- **扩展**应用程序的地图功能,包括使用[地理编码](/help/glossary/geocoding/)、路径分析、空间分析等的Web服务。以简单代码创建静态地图。


- **Create** static maps programmatically.

- 以代码**创建**静态地图。

## Use Mapbox map data

{{
  <GLWrapper><HmwMapSources /></GLWrapper>
}}

Our core [tilesets](/help/glossary/tileset/): Mapbox Streets, Mapbox Terrain, Mapbox Traffic, and Mapbox Satellite. Each tileset contains a unique set of data from a variety of sources.

- **Mapbox Streets** includes streets, buildings, administrative areas, water, and land data based on [OpenStreetMap](http://www.openstreetmap.org/), updated as often as every five minutes.
- **Mapbox Terrain** includes landcover data and a worldwide elevation data set complete with contours, hillshade, and elevation data.
- **Mapbox Satellite**  includes global satellite imagery from [a range of sources](https://www.mapbox.com/about/maps), processed and seamed together by Mapbox.
- **Mapbox Traffic** includes regularly updated vehicle congestion information on top of Mapbox Streets.

You can find a full list of layers available in the Mapbox Streets, Terrain, and Traffic sources in our [Vector Tiles overview](https://www.mapbox.com/vector-tiles/). You can read more about our data sources on our [Maps page](https://www.mapbox.com/about/maps).

<a className="txt-bold" href="/help/how-mapbox-works/mapbox-data/">{{<ChevronousText text="Learn about our data" />}}</a>

## 使用MapBox地图数据

   主要的[瓦片地图](/help/glossary/tileset/)：Mapbox街道瓦片地图、Mapbox地形瓦片地图和Mapbox卫星瓦片地图。每一个瓦片地图有着各自不同的数据源。
   
   - **MapBox街道地图**包括基于OpenStreetMap的数据的建筑物，行政区域，水域和土地数据[OpenStreetMap](http://www.openstreetmap.org/)，每五分钟更新一次。
   
   - **MapBox地形地图**包括土地覆盖数据和全球高程数据——轮廓、山体阴影和高程数据。
   - **MapBox卫星地图**包括各种来源的[全球卫星图像](https://www.mapbox.com/about/maps)，由Mapbox处理和拼接。
   - **MapBox交通地图**包括MapBox街道地图定期更新的车辆拥堵信息。
   
  您可以在[矢量瓦片地图概览](https://www.mapbox.com/vector-tiles/)中找到Mapbox 街道地图，地形地图和交通地图，可以查看完整的地图类型列表。您可以在我们的[地图页面](https://www.mapbox.com/about/maps)上详细了解我们的数据来源。

## Design a map

Custom map design is one of the core functions of Mapbox Studio. We provide an advanced application for putting this customization at your fingertips with the Mapbox Studio style editor. In Mapbox Studio, you can start with one of our [template styles](https://www.mapbox.com/maps/) or [designer styles](https://www.mapbox.com/designer-maps/) and style each individual layer to your exact specification.

{{
  <DemoIframe src="/help/demos/how-mapbox-works/map-design.html" />
}}

On the left you can see the **Basic style**, a template style made up of a limited set of layers. On the right you can see a **custom style** that uses all the same underlying data, but that has been customized by changing colors and fonts in Mapbox Studio style editor.

The [Mapbox Studio style editor](https://www.mapbox.com/studio/styles) is a full-featured map editor that gives you total control over the style of your map directly in your browser. Whether you start with a Mapbox template style or start from scratch, the styling possibilities are virtually endless. With the Mapbox Studio style editor, you can:

- Create styles that change dynamically based on zoom level.
- Use custom fonts.
- Set custom alignment, pitch, offset, and more for your labels.
- Set colors, weights, and opacity for your map layers.
- Filter tilesets based on attributes.

<a className="txt-bold" href="/help/how-mapbox-works/map-design/">{{<ChevronousText text="Learn about map design" />}}</a>

## 设计一个地图

  自定义地图样式是MapBox Studio的核心功能之一。我们提供了一个高级应用，使用Mapbox Studio样式编辑器，将此自定义设置地图样式。在mapbox studio中，您可以从我们的[模板样式](https://www.mapbox.com/maps/)或[设计样式](https://www.mapbox.com/designer-maps/)中的一种地图样式开始，并根据您的具体规范设置每个单独的图层样式。

  在Mapbox Studio左侧，您可以看到**基本样式**，即由一组有限图层组成的模板样式。在右侧，您可以看到使用所有相同基础数据的**自定义样式**，但该样式是通过在Mapbox Studio样式编辑器中更改颜色和字体进行自定义设置。
  
  [Mapbox studio样式编辑器](https://www.mapbox.com/studio/styles)是一个功能齐全的地图编辑器，您可以直接在浏览器中完全控制地图的样式。无论是从Mapbox模板样式开始还是自定义开始，样式设置的可能性实际上是无穷的。使用Mapbox Studio样式编辑器，可以：
  
  - 创建基于缩放级别动态更改的样式。
  - 使用自定义字体。
  - 为标签设置自定义对齐、间距、偏移等。
  - 为地图图层设置颜色、权重和透明度。
  - 根据属性条件进行瓦片设置。
 
  
## Add custom data

Mapbox provides robust geospatial data with our Streets, Terrain, Traffic, and Satellite tilesets, but mapping applications often require custom data. To add custom data to your map, you can upload your own data as [tilesets](/help/glossary/tileset) or create [datasets](/help/glossary/dataset).

**Tilesets and datasets are two different types of data**: tilesets are styleable and datasets are editable. Styling includes changing things like color, opacity, font, or icon. Editing includes changing the placement of features (points, lines, polygons), their geometries, and adding or deleting features from a feature collection. If you have created or imported a dataset, you can export your dataset to a tileset right in Mapbox Studio and use it in the Mapbox Studio style editor like you would any other tileset.

## 添加自定义数据

  Mapbox的街道、地形、交通和卫星瓦片地图提供了大量的地理空间数据，但地图应用程序通常需要自定义数据。要将自定义数据添加到地图，可以将自己的数据上传为[瓦片数据](/help/glossary/tileset)或[创建数据集](/help/glossary/dataset)。
  
  **瓦片数据和数据集是两种不同类型的数据**：瓦片数据是可以进行地图样式渲染，数据集数据是可以数据编辑的。地图样式渲染包括改变要素的颜色、透明度、字体或者图标等。数据编辑包括改变要素的位置（多点、多线、多面），改变要素的几何构造并且可以增加或者删除要素上的某些要素集合。如果你创建或者导入了一个要素集，那么你就可以在MapBox studio中导出正确合适瓦片并且你可以在MapBox studio中编辑你想要的任何要素。

### Upload tilesets

Tilesets are lightweight collections of vector data that are optimized for rendering and are not editable. When you [upload custom data](/help/troubleshooting/uploads), your files are converted to vector tilesets, which can be styled in the Mapbox Studio style editor, added to [interactive web maps with Mapbox GL JS](https://www.mapbox.com/mapbox-gl-js/example/queryrenderedfeatures/), and used in mobile applications created with the Mapbox Maps SDKs for [iOS](https://docs.mapbox.com/ios/maps/overview/) and [Android](https://docs.mapbox.com/android/maps/overview/).

For more details about accepted file types and methods for uploading data, see the [Uploading data guide](/help/how-mapbox-works/uploading-data/).

<a className='txt-bold' href="/help/how-mapbox-works/uploading-data/">{{<ChevronousText text="Learn about uploads" />}}</a>

### 上传瓦片数据

  瓦片地图是矢量数据的轻量级集合，为渲染而优化，不可编辑。[上传自定义数据时](/help/troubleshooting/uploads)，文件将转换为矢量瓦片，可以在Mapbox Studio样式编辑器中设置样式，使用[Mapbox GL JS](https://www.mapbox.com/mapbox-gl-js/example/queryrenderedfeatures/)添加到交互式Web地图中，并用于使用Mapbox Maps SDK为[iOS](https://docs.mapbox.com/ios/maps/overview/)和[Android](https://docs.mapbox.com/android/maps/overview/)创建的移动应用程序。
  
  有关可接受的文件类型和数据上传的方法的详细信息，可以参阅[《数据上传指南》](/help/how-mapbox-works/uploading-data/)。


### Create datasets

A dataset is an editable collection of [GeoJSON features](https://tools.ietf.org/html/rfc7946). A feature stored with Mapbox has both geometries and properties (attributes), both of which can be edited in the Mapbox Studio dataset editor or through the Mapbox Datasets API. You can use the [dataset editor](https://www.mapbox.com/studio-manual/reference/datasets) in Mapbox Studio to import, create, and edit GeoJSON point, line, and polygon features and their properties. Once you've finished working with your dataset, you can export it to a tileset for use with the Mapbox Studio [style editor](https://www.mapbox.com/studio/). There are limits to how much data you can load into the Mapbox Studio dataset editor at a time, but you can use the Mapbox [Datasets API](https://docs.mapbox.com/api/maps/#datasets) to add more features and manage them programmatically.

<img alt="animated GIF demonstrating how to modify a feature in the Mapbox studio dataset editor" className='px0 py0 mx0 my0' src="/help/img/studio/dataset-modify-feature.gif" />

For more details about accepted file types and methods for creating datasets, see the [Creating new data guide](/help/how-mapbox-works/creating-data/).


<a className='link txt-ms txt-bold' href="/help/how-mapbox-works/creating-data/">{{<ChevronousText text="Learn about creating data" />}}</a>

### 创建数据集

  一个可以编辑的数据集合应该是[GeoJSON格式的要素](https://tools.ietf.org/html/rfc7946)。要素存储在MapBox中必须具有几何属性和特征属性，两者都可以在MapBox studio数据集编辑器中编辑或通过调用MapBox的API进行编辑。可以使用Mapbox Studio中的[数据集编辑器](https://www.mapbox.com/studio-manual/reference/datasets) 导入、创建和编辑GeoJSON点、线和多边形要素及其属性。处理完数据集后，可以将其导出到tileset，以便与MapBox studio[样式编辑器](https://www.mapbox.com/studio/)一起使用。一次可以加载到MapBox studio数据集编辑器中的数据量是有限的，但是可以使用MapBox[数据集API](https://docs.mapbox.com/api/maps/#datasets)添加更多功能并以代码编辑的方式管理它们。
  
  <img alt=" 动画gif演示如何在MapBox studio数据集编辑器中修改功能" className='px0 py0 mx0 my0' src="/help/img/studio/dataset-modify-feature.gif" />
  
  有关接受的文件类型和创建数据集的方法的更多详细信息，请参阅[创建新数据指南](/help/how-mapbox-works/creating-data/)。


  
## Build applications

Once you've created, styled, and added data to your map, Mapbox provides multiple tools for integrating your maps into a website or custom application.

### 创建一个地图应用
  
  如果您已经创建了地图、设置了地图样式并将数据添加到地图中，MapBox将提供多种工具来将地图集成到网站或自定义地图应用程序中。

### Web applications

You can use one of our JavaScript libraries to publish your map to the web.

{{
  <DemoIframe src="/help/demos/gl-store-locator/step-five.html" />
}}


This web application uses a combination of HTML, CSS, JavaScript, and  **Mapbox GL JS**, our WebGL-based JavaScript library. If you are interested in learning more about how to build an application like this one, read our step-by-step [Build a store locator](/help/tutorials/building-a-store-locator/) tutorial.


[Mapbox GL JS](https://www.mapbox.com/mapbox-gl-js/) is a JavaScript library for creating interactive, customizable maps from Mapbox styles and vector tiles. Mapbox GL JS uses WebGL, a technology used to create video games in the browser, which enables you to build advanced interactions into your maps, including smooth zooming, map bearing and pitch, querying underlying map data, and dynamically filtering the data you choose to display. You can use the custom styles you've created in the Mapbox Studio style editor or any of the template styles we provide, plus add any additional data you want programmatically -- including GeoJSON, images, and even [video](https://www.mapbox.com/mapbox-gl-js/example/video-on-a-map/)! Be sure to explore the [Mapbox GL JS examples](https://www.mapbox.com/mapbox-gl-js/examples) for dozens of other interactive examples.

[Mapbox.js](https://www.mapbox.com/mapbox.js/) is our older JavaScript web mapping library that extends the popular [Leaflet.js](http://leafletjs.com) library. Mapbox.js can be used to create interactive maps with [classic styles](/help/glossary/classic-style/).


<a className="txt-bold" href="/help/how-mapbox-works/web-apps">{{<ChevronousText text="Learn about web apps" />}}</a>

### Web地图应用
  您可以使用我们的JavaScript库之一将您的地图发布到网络上。
  
  这个Web应用程序使用HTML、CSS、JavaScript GL JS的组合，**Mapbox GL JS**是我们基于Web-GL的JavaScript库。如果您对如何构建这样的应用程序感兴趣，请阅读我们的分步[构建教程](/help/tutorials/building-a-store-locator/)。
  
  [Mapbox GL JS](https://www.mapbox.com/mapbox-gl-js/)是一个JavaScript库，用于从Mapbox样式和矢量瓦片创建交互式的、可自定义的地图。Mapbox GL JS使用WebGL，这是一种用于在浏览器中创建视频游戏的技术，它使您能够在地图中构建高级交互，包括地图缩放、地图方位和俯仰、基础地图数据查询以及动态过滤您选择显示的数据。您可以使用在Mapbox Studio样式编辑器中创建的自定义样式或我们提供的任何模板样式，还可以通过代码添加您想要的任何其他数据，包括geojson、图像甚至[视频](https://www.mapbox.com/mapbox-gl-js/example/video-on-a-map/)！你可以在[Mapbox GL JS示例](https://www.mapbox.com/mapbox-gl-js/examples)中探索其他许多交互式示例。
  [Mapbox.js](https://www.mapbox.com/mapbox.js/)是我们先前的JavaScript Web地图库，它扩展了流行的[Leaflet.js](/help/glossary/classic-style/)库。 Mapbox.js可用于创建具有[经典样式](/help/glossary/classic-style/)的交互式地图。

### Mobile applications

Mapbox provides a Maps SDK for [iOS](https://www.mapbox.com/ios-sdk/) and [Android](https://www.mapbox.com/android-docs/) for publishing your maps in native applications. The Maps SDKs for iOS and Android are designed to be drop-in replacements for Apple's MapKit and the Google Maps SDKs. The Maps SDKs should be familiar to mobile developers who have experience with either. Often, your maps can be swapped for Mapbox by changing a single line of code.

![Mapbox maps on a mobile device](/help/img/screenshots/mobile.png)

Each SDK comes bundled with five Mapbox-designed map styles and can handle any custom design created with the [Mapbox Studio style editor](https://www.mapbox.com/studio/). If you use one of Mapbox's mobile SDKs, you'll also get access to the [mobile usage dashboard](https://www.mapbox.com/account/statistics), which provides a continuously updated view of monthly active users, map usage, and region-by-region metrics.


<a className="txt-bold" href="/help/how-mapbox-works/mobile-apps/">{{<ChevronousText text="Learn about mobile apps" />}}</a>

 ### 移动端地图应用：
 
  Mapbox为[IOS](https://www.mapbox.com/ios-sdk/)和[Android](https://www.mapbox.com/android-docs/)提供了一个Maps SDK，用于在本地应用程序中发布地图。IOS和Android的Maps SDK是苹果Mapkit和Googlemaps SDK的替代产品。Maps-SDK对于有这两方面经验的移动开发人员来说应该很熟悉。通常，可以通过更改 一行代码将地图替换为MapBox。
  
  ![移动设备上的地图框地图](/help/img/screenshots/mobile.png)
  
  每个SDK绑定了五种Mapbox设计的地图样式，可以处理使用Mapbox Studio样式[编辑器](https://www.mapbox.com/studio/)创建自定义地图样式。如果您使用Mapbox的一个移动SDK，您还可以访问移动端使用的[数据统计界面](https://www.mapbox.com/account/statistics)，该数据统计界面提供每月活动用户、地图使用情况和按区域度量的连续更新视图。

### Unity applications

![Mapbox SDK for Unity sample image](/help/img/unity/games.jpg)

Mapbox makes real world simulations possible by giving you the tools to put real world maps in your Unity applications. The [Mapbox Maps SDK for Unity](/help/glossary/mapbox-maps-sdk-for-unity/) is a set of tools to build Unity applications from real map data. It consists of a robust API for interfacing with Mapbox web services and converting map resources into game objects as well as a robust graphical user interface built on top of the Unity platform.


<a className="txt-bold" href="/help/how-mapbox-works/unity/">{{<ChevronousText text="Learn about Unity apps" />}}</a>

### Unity地图应用

  ![MapBox SDK for Unity示例图片](/help/img/unity/games.jpg)
  
  MapBox SDK for Unity应用程序中放置真实世界地图的工具，模拟真实世界成为可能。[MapBox SDK for Unity](/help/glossary/mapbox-maps-sdk-for-unity/)是用于从真实的地图数据构建unity应用程序。它包括一个强大的API，用于与Mapbox Web服务交互，将地图资源转换为游戏对象，以及一个健壮的图形用户界面，该界面构建在unity平台之上。


## Extend your application

Besides designing maps and publishing mapping applications, Mapbox also has tools for interacting with data, locating addresses, conducting spatial analysis, and routing. Our web services APIs are building blocks you can use to make your maps interactive and dynamic.

## 拓展您的地图应用

除了设计地图和发布地图应用程序外，mapbox还提供了与数据交互、定位地址、进行空间分析和路径导航的工具。我们提供Web API的服务，使用API中提供的方法会使地图具有交互性和动态性。

### Mapbox Geocoding API

Add global place search to your app with the [Mapbox Geocoding API](https://docs.mapbox.com/api/search/#geocoding). Turn latitude and longitude values into addresses with **reverse geocoding** or you turn addresses into latitude and longitude values with **forward geocoding**. You can use the Geocoding API right in your web or mobile application or as a standalone service.


![animation demonstrating geocoding with autocomplete](/help/img/api/geocode.gif)

<a className="txt-bold" href="/help/how-mapbox-works/geocoding/">{{<ChevronousText text="Learn about geocoding" />}}</a>

### MapBox 地理编码API

使用[Mapbox地理编码API](https://docs.mapbox.com/api/search/#geocoding)将全局位置搜索添加到应用程序中。使用**反向地理编码**将纬度和经度值转换为地址，或者使用**正向地理编码**将地址转换为纬度和经度值。您可以在Web或移动应用程序中使用地理编码API，也可以将其作为独立服务使用。

![用自动完成演示地理编码的动画](/help/img/api/geocode.gif)


### Mapbox Directions API

The Mapbox [Directions API](https://docs.mapbox.com/api/navigation/#directions) provides point-to-point directions for walking, cycling, or driving based on the wide network of roads and paths in OpenStreetMap. The Directions API returns text instructions, alternative routes, geometry (for drawing routes), and maneuvers. The Directions API also powers our [Map matching](https://docs.mapbox.com/api/navigation/#map-matching), [Matrix](https://docs.mapbox.com/api/navigation/#matrix), and [Optimization](https://docs.mapbox.com/api/navigation/#optimization) APIs. See the [Directions API documentation](https://docs.mapbox.com/api/navigation/#directions) for more information.

![screenshot of the Mapbox GL JS directions plugin on a map](/help/img/directions/gljs-plugin.png)

<a className="txt-bold" href="/help/how-mapbox-works/directions">{{<ChevronousText text="Learn about directions" />}}</a>

### MapBox路径导航API

[Mapbox Directions API](https://docs.mapbox.com/api/navigation/#directions)基于OpenStreetMap中众多的道路和路网为步行、骑自行车或驾驶提供点到点的方向导航。导航API返回文本指令、替代路线、几何图形（用于绘制路线）和动态导航。路径导航API还支持我们的[地图匹配](https://docs.mapbox.com/api/navigation/#map-matching)、[路网](https://docs.mapbox.com/api/navigation/#matrix)和[路径优化](https://docs.mapbox.com/api/navigation/#optimization)API。有关更多信息，请参阅[路径导航API文档](https://docs.mapbox.com/api/navigation/#directions)。

![地图上Mapbox GL JS 导航插件的屏幕截图](/help/img/directions/gljs-plugin.png)


### Analyze with Turf.js

[Turf.js](http://turfjs.org/) is an open source JavaScript library for spatial analysis. Turf includes traditional spatial analysis operations, helper functions for creating GeoJSON data, and data classification and statistics tools. You can add Turf to your website as a client-side plugin, or you can run Turf server-side with Node.js.

![screenshot of a Turf example](/help/img/turf/turf.png)

<a className="txt-bold" href="/help/how-mapbox-works/geospatial-analysis/">{{<ChevronousText text="Learn about analysis" />}}</a>

### 使用Turf.js分析

[Turf.js](http://turfjs.org/)是一个用于空间分析的开源Javascript库。Turf.js包括传统的空间分析操作、用于创建GeoJSON数据的帮助函数以及数据分类和统计工具。您可以将Turf.作为客户端插件添加到网站，也可以使用node.js运行Turf服务器。

![一个Turf.js例子的截图](/help/img/turf/turf.png)


## Use satellite imagery

Mapbox Satellite is a global basemap of continuous satellite and aerial imagery that you can use as a blank canvas or an overlay for your own data. Comprised of multiple imagery sources, we color correct it and update it as new imagery becomes available.

![samples of Mapbox satellite imagery](/help/img/satellite/satellite.png)

Mapbox Satellite uses global satellite and aerial imagery from commercial providers, NASA, and USGS. As cities grow and landscapes change, we add newer, clearer, and more attractive imagery.

The current zoom level offerings include:

- 0–8: MODIS 2012–2013.
- 9–12: Landsat 5 & 7, 2010–2011.
- 13–19: a combination of open and proprietary sources, including DigitalGlobe’s GBM 2011+ for much of the world, USDA’s NAIP 2011–2013 in the contiguous United States, and open aerial imagery from Denmark, Finland, and parts of Germany.


<a className="txt-bold" href="/help/how-mapbox-works/satellite-imagery/">{{<ChevronousText text="Learn about satellite imagery" />}}</a>

## 使用卫星影像

Mapbox 卫星影像是连续卫星和航空图像的全球基础地图，您可以将其用作自己数据的底图或覆盖。由多个图像源组成，我们对其进行颜色校正，并在新图像可用时进行更新。

![Mapbox的卫星影像服务的例子](/help/img/satellite/satellite.png)

Mapbox卫星影像服务使用全球卫星和来自商业卫星提供商、NASA和USGS的航空图像。随着城市的发展和景观的变化，我们增加了更新、清晰和更有吸引力的图像。

目前的可提供的分辨率级别包括：

- 0–8: MODIS 2012–2013.
- 9–12: Landsat 5 & 7, 2010–2011.
- 13–19：公开和专有资源的组合，包括DigitalGlobe的GBM 2011+，美国农业部的NAIP 2011-2013，以及丹麦、芬兰和德国部分地区的公开遥感图像。

## Create static maps

The Mapbox [Static Images API](https://docs.mapbox.com/api/maps/#static-images) can generate static images from your map styles. Provide your style ID, access token, and a few more parameters &mdash; such as zoom, bearing, pitch, and overlay &mdash; and you can display static images directly by making requests in your application.

{{
  <DemoStatic src="https://api.mapbox.com/styles/v1/mapbox/streets-v{constants.VERSION_STREETS_STYLE}/static/pin-s-a+9ed4bd(-122.46589,37.77343),pin-s-b+000(-122.42816,37.75965),path-5+f44-0.5(%7DrpeFxbnjVsFwdAvr@cHgFor@jEmAlFmEMwM_FuItCkOi@wc@bg@wBSgM)/auto/800x300@2x?access_token=MapboxAccessToken" alt="static Mapbox map with route and point overlays" />
}}

<a className="txt-bold" href="/help/how-mapbox-works/static-maps/">{{<ChevronousText text="Learn about static maps" />}}</a>

## 创建一个静态地图

MapBox[静态地图API](https://docs.mapbox.com/api/maps/#static-images)可以从地图样式生成静态图像。提供您的样式id、访问token和一些其他参数（如缩放、方向角、俯仰角和图层），您可以通过在应用程序中发出请求来直接调用显示静态地图。


## Add attribution

Whether you're creating a custom style with Mapbox Studio or building a mobile app with the Android SDK, all Mapbox tools require [attribution](/help/how-mapbox-works/attribution) according to our [terms of service](https://www.mapbox.com/tos).

<a className="txt-bold" href="/help/how-mapbox-works/attribution">{{<ChevronousText text="Learn about attribution" />}}</a>

## 添加属性

无论您是使用mapbox studio创建自定义样式，还是使用android sdk创建移动应用程序，所有Mapbox工具都需要根据我们的[服务条款](https://www.mapbox.com/tos)进行[归档](/help/how-mapbox-works/attribution)。

