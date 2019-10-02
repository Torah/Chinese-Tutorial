---
title: Create new data
description: Learn how datasets work and how to create geospatial data from scratch using Mapbox.
image: /img/narrative/data-create.svg
topics:
  - datasets
prependJs:
  - "import * as constants from '../../constants';"
  - "import { HmwDemo } from '../../components/hmw-demo';"
  - "import { datasetSample } from '../../snippets/dataset';"
contentType: guide
---
一个**数据集（dataset）**是一个可编辑的[GeoJSON](/help/glossary/geojson/) [features](/help/glossary/features/)集合。与[tileset](/help/glossary/tileset)不同，数据集可以逐特征编辑。数据集不能被直接在Mapbox Studio样式里使用但是可以被输出成一个tileset或通过Mapbox GL JS渲染。任何被输出成tileset的数据集都可以作为一个图层加载到Mapbox Studio样式编辑器中。
A **dataset** is an editable collection of [GeoJSON](/help/glossary/geojson/) [features](/help/glossary/features/). Unlike [tilesets](/help/glossary/tileset), datasets can be edited on a feature-by-feature basis. Datasets cannot be used directly in a Mapbox Studio style but can be exported as a tileset or rendered with Mapbox GL JS. Any dataset exported to a tileset can be added as a layer in the Mapbox Studio style editor.
<!--copyeditor ignore url-->
{{
    <HmwDemo
      visual={{
        title: "Mapbox Studio dataset editor",
        subtitle: "Use the dataset editor to create and manage your data",
        content: <div className='h300' style={{backgroundImage: "url(/help/img/studio/how-datasets-work.png)", backgroundSize: "cover"}}></div>
      }}
      code={{
        title: "Dataset",
        subtitle: "Sample GeoJSON FeatureCollection",
        content: <pre id='style-spec' className='txt-xs px12 mx0 my0 h300' style={{overflowY: "scroll"}}>
            {datasetSample}
        </pre>
      }}
    />
}}

在这个例子中，您可以看到在**Mapbox Studio数据集编辑器**里面，一个数据集的视觉表示在左边，**数据集**的实际内容，一个GeoJSON FeatureCollection在右边。这些数据集的内容包括形状和在左边可以看到的每个点的属性，但是不包括任何样式的信息。请参考[上传数据](/help/how-mapbox-works/uploading-data/)指南来获得更多关于改变点的样式（如具体改变符号、颜色、标注字体）的信息，里面也包括了如何将数据集转换为tileset。
In this example, you can see a visual representation of a dataset inside the **Mapbox Studio dataset editor** on the left and the actual contents of the **dataset**, a GeoJSON FeatureCollection, on the right. The contents of the dataset include geometry and properties for each point that you can see on the left, but does not contain any style information. For more details on how to style the points (for example, specify the symbols, colors, and the font for labels), see the [Upload data](/help/how-mapbox-works/uploading-data/) guide, which covers converting datasets to tilesets.


## 数据集是怎么运作的
## How datasets work

数据集是您的**[GeoJSON](http://geojson.org/)**原始数据的一个托管的版本。您可以用数据集编辑器或[Mapbox Datasets API](https://docs.mapbox.com/api/maps/#datasets)访问并编辑您的数据集。
Datasets are a hosted version of your raw data as **[GeoJSON](http://geojson.org/)**. You can access and edit your datasets with the dataset editor or the [Mapbox Datasets API](https://docs.mapbox.com/api/maps/#datasets).


### 格式
### Format

<div class='fr pl12' style='width:50%'>
<pre>
{
    "id": "{feature_id}",
    "type": "Feature",
    "geometry": {
        "type": "Point",
        "coordinates": [0, 0]
    },
    "properties": {
        "name": "null island"
    }
}
</pre>
</div>


数据集以**[GeoJSON](http://geojson.org/)**形式存储，这是Mapbox[网络服务及API](https://www.mapbox.com/developers/api/)通常用以编码各种地理数据的格式。基于[JSON](http://www.json.org/) (JavaScript object notation)，GeoJSON源自于JavaScript语言且可以在现代软件中被解析出来。
Datasets are stored as **[GeoJSON](http://geojson.org/)**, a format for encoding a variety of geographic data often used by Mapbox [web services and APIs](https://www.mapbox.com/developers/api/). Based on [JSON](http://www.json.org/) (JavaScript object notation), GeoJSON is native to the JavaScript language and can be parsed in modern software.


Mapbox将数据集要素存储为一系列的GeoJSON要素。要素是单个的（在某些情况下是一组）点、线、或多边形。Mapbox Datasets API不支持GeometryCollections或地理信息空值。每个特征都被其地理信息和属性所定义：
Mapbox stores dataset features as collections of GeoJSON features. Features are individual (or in some cases groups of) points, lines, or polygons. The Mapbox Datasets API does not support GeometryCollections or null geometries. Each feature is defined by its geometry and properties:

- **图形信息**：用于描述每个特征的形状和位置。您可以具体说明是（Points）、线（LineStrings）、还是多边形（Polygons）。每个特征的位置和具体形状都被具体坐标所定义。
- **Geometry**: This describes the shape and the location of each feature. You can specify Points, LineStrings, Polygons. The location and the exact shape of each feature is determined by the coordinates that are specified.
- **属性**：它可以包含任意JSON物体。一些用于Mapbox数据集常见属性的例子里包括在Web应用中的弹窗里的`title`和`description`。
- **Properties**: This can contain any JSON object. Some examples of common properties that are applied to Mapbox datasets include `title` and `description` to include in popups in a web application.


### 数据集转换为tileset的过程
### Dataset to tileset process


您不能把数据集直接添加到Mapbox Studio样式编辑器的样式里。但是您可以将数据集输出为tileset，然后再添加到Mapbox Studio样式编辑器或Mapbox GL JS中。当您将数据集输出为tileset的时候，它的处理方式和上传数据的处理方式是一样的。
You cannot add datasets directly to styles in the Mapbox Studio style editor. But you can export your dataset as a tileset and add it to your style in the Mapbox Studio style editor or Mapbox GL JS. When you export your dataset to a tileset, it is processed in the same way an upload would be processed.

您可以在[上传数据][Upload data](/help/how-mapbox-works/uploading-data/)指南里阅读更多关于如何把原始数据变为tileset。
You can read more about how raw data becomes a tileset in the [Upload data](/help/how-mapbox-works/uploading-data/) guide.


### 下载数据集
### Downloading datasets


当您创建了一个数据集的时候，您可以将它输出为一个tileset以在Mapbox地图里使用（参照[地图设计指南](/help/how-mapbox-works/map-design/)以获得更多信息），下载为一个GeoJSON FeatureCollection，或用Mapbox Datasets API获取。数据集在被输出后还可以被编辑，但如果您希望本地版本能够反映出所有改动的话，您需要保证同步更新您的近期修改到下载的版本。
Once you’ve created a dataset, you can export it to a tileset for use in a Mapbox map (see the [How map design works guide](/help/how-mapbox-works/map-design/) for more information), download it as a GeoJSON FeatureCollection, or access it with the Mapbox Datasets API. Datasets can still be edited after export, but you will need to make sure to sync your downloaded version with your new edits if you would like your local copy to reflect any changes you've made.

请参考[Mapbox Studio手册数据集部分](https://www.mapbox.com/studio-manual/reference/datasets/)来了解如何下载和输出数据集。
To learn how to download and export datasets, see the [datasets section of the Mapbox Studio Manual](https://www.mapbox.com/studio-manual/reference/datasets/).


## 创建数据集
## Creating datasets


您可以在Mapbox Studio[数据集编辑器](https://www.mapbox.com/studio/datasets/)或通过[Mapbox Datasets API](https://docs.mapbox.com/api/maps/#datasets)从头创建一个数据集。注意在每个案例中，这个过程会包括两个步骤：创建一个空数据集，和加载要素到数据集中。
You can create a dataset from scratch in the Mapbox Studio [dataset editor](https://www.mapbox.com/studio/datasets/) or through the [Mapbox Datasets API](https://docs.mapbox.com/api/maps/#datasets). Note that the process involves two steps in each case: creating an empty dataset, and adding features to that dataset.


### Mapbox Studio
### Mapbox Studio


在Mapbox Studio中，您可以使用数据集编辑器通过可视界面而非直接写GeoJSON来创建一个新的数据集。为了使用Mapbox Studio数据集编辑器来创建数据集，您可以创建一个新的空数据集再通过在数据集编辑器里绘制特征以添加它们，您也可以上传一个GeoJSON或CSV文件作为数据集，然后用数据集编辑界面编辑、添加、删除特征。
In Mapbox Studio, you can use the dataset editor to create a new dataset using a visual interface rather than writing the GeoJSON directly. To create a dataset with the Mapbox Studio dataset editor, you can either create a new empty dataset and add features to it by drawing them in the dataset editor, or you can upload a GeoJSON or CSV file as a dataset and edit, add, and delete features using the dataset editor interface.


您可以参照[Mapbox Studio手册](https://www.mapbox.com/studio-manual/reference/datasets/)了解更多关于如何用Mapbox Studio数据集编辑器创建数据集的内容。
You can learn more about how to create datasets using the Mapbox Studio dataset editor in the [Mapbox Studio Manual](https://www.mapbox.com/studio-manual/reference/datasets/).


### Mapbox Datasets API
### Mapbox Datasets API


利用Mapbox Datasets API，您可以通过请求[插入要素](https://docs.mapbox.com/api/maps/#insert-or-update-a-feature)来添加要素。您不能通过Datasets API直接上传文件。Datasets API一次只能接收一个特征。如果您想要从FeatureCollection添加许多特征的话，您可以通过编程完成。
Using the Mapbox Datasets API, you can add features by making requests to [insert a feature](https://docs.mapbox.com/api/maps/#insert-or-update-a-feature). You cannot upload a file directly through the Datasets API. The Datasets API accepts one Feature at a time. If you would like to add many Features from a FeatureCollection, you can do so programmatically.


请参考[Mapbox Datasets API 文档](https://docs.mapbox.com/api/maps/#datasets)来获取更多关于如何通过编程更新数据集的内容。
You can read more about how to programmatically update datasets in the [Mapbox Datasets API documentation](https://docs.mapbox.com/api/maps/#datasets).
