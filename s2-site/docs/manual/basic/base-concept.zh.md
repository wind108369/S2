---
title: 基本概念
order: 0
---
交叉表的基本概念

## 简介

交叉表由五部分组成，分别是行头、列头、角头、单元格 (data-cell)、框架 (frame)，如下图所示：

![s2](https://gw.alipayobjects.com/mdn/rms_56cbb2/afts/img/A*nzcERYjsPZoAAAAAAAAAAAAAARQnAQ)

（需替换）

## 行头（rowHeader）

行头的结构是由 `dataCfg.fields.rows` 决定，通常情况下是用于行分析维度展示。

比如行头数据配置为 `rows: ['province', 'city']`，在平铺模式下展示为：

<img src="https://gw.alipayobjects.com/mdn/rms_56cbb2/afts/img/A*Ezh7RY41R90AAAAAAAAAAAAAARQnAQ" width = "250"  alt="row" />

在树状模式下展示为：

<img src="https://gw.alipayobjects.com/mdn/rms_56cbb2/afts/img/A*Nj2lQaDPmN0AAAAAAAAAAAAAARQnAQ" height = "200"  alt="column" />

## 列头（colHeader）

列头的结构是由 `dataCfg.fields.columns` 决定，通常情况下是用于列分析维度展示。

比如行头数据配置为 `columns: ['type', 'sub_type']`，展示为：

<img src="https://gw.alipayobjects.com/mdn/rms_56cbb2/afts/img/A*GNirRr5HANUAAAAAAAAAAAAAARQnAQ" width = "400"  alt="column" />

> 注意，当 `sheetType: 'table'` 时，需且仅需设置 columns。

## 角头（cornerHeader）

角头是左上角部分，在表的布局中起到至关重要的作用。

表的布局中，`S2` 是以角头作为基础进行扩展，计算出行、列的尺寸和坐标。

角头也用于展示行头名称，比如示例中的`省份`、`城市`。

另外，`S2` 还提供了自定义扩展，用于需要自定义角头的场景，详见 [cornerCell](待补充） 和 [cornerHeader]（待补充)。

## 单元格 (dataCell)

单元格是表格行列维度值交叉后产生的数据区域，通常情况下应该是度量值，是用于表数据分析最核心的数据呈现区域。

在单元格区域，我们可以展现基础的交叉数据，可以通过 [条件格式](待补充）来辅助增强分析，也可以展现同环比等衍生指标，还可以通过自定义 Hooks 来实现单元格自定义，更多参考 [dataCell]（待补充)。

## 框架（frame）

`S2`布局中，框架位于其他四个区域之上，用来做区域之间的间隔框架，或者滚动条，框架间隔线的阴影等逻辑。在使用过程不用关心框架的概念，但做二次开发时，需要注意框架的层级和容器属性。