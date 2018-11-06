# webmagic core

## Task

* 用于识别不同任务的接口

详情见[Task.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/Task.java)

## Spider

* 实现Runable和Task接口

* 爬虫入口

* 爬虫包含四个模块：Downloader, Scheduler, PageProcessor 和 Pipeline，每个模块都是爬虫的一个属性。

详情见[Site.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/Spider.java)

## SpiderListener

* 用于Process上Spider的监听的接口，主要用于监听器。

详情见[Site.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/SpiderListener.java)

## Site

webmagic常见配置项

详情见[Site.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/Site.java)

## ResultItems

* 封装抽取结果的对象

* 它包含在Page中，将在pipeline中处理

详情见[ResultItems.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/ResultItems.java)

## Request

* 封装爬虫Url的对象

* 增加了额外的属性

详情见[Request.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/Request.java)

## Page

* 封装存储提取的结果和要获取的URL

* 非线程安全

详情见[Page.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/Page.java)

## downloader

### Downloader

* 网页下载和存储接口

* 支持线程数配置

详情见[Downloader.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/downloader/Downloader.java)

### AbstractDownloader

* 实现Downloader接口

* 增加额外方法

详情见[AbstractDownloader.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/downloader/AbstractDownloader.java)

### CustomRedirectStrategy

* 支持POST 302跳转策略

详情见[CustomRedirectStrategy.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/downloader/CustomRedirectStrategy.java)

### HttpClientDownloader

* 继承AbstractDownloader

* 基于http client实现downloader

详情见[HttpClientDownloader.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/downloader/HttpClientDownloader.java)

### HttpClientGenerator

* http client生成器

详情见[HttpClientGenerator.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/downloader/HttpClientGenerator.java)

### HttpClientRequestContext

* http client请求和上下文封装

详情见[HttpClientRequestContext.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/downloader/HttpClientRequestContext.java)

## model

### HttpRequestBody

* http请求消息体

详情见[HttpRequestBody.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/model/HttpRequestBody.java)

## pipeline

### Pipeline

* Pipeline是爬虫的持久和脱机过程的一部分。

* 可以定制持久性方式的接口。

详情见[Pipeline.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/pipeline/Pipeline.java)

### CollectorPipeline

* 扩展Pipeline接口，增加集合处理功能

详情见[CollectorPipeline.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/pipeline/CollectorPipeline.java)

### ConsolePipeline

* 结果输出到控制台管道

详情见[ConsolePipeline.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/pipeline/ConsolePipeline.java)

### FilePipeline

* 结果输出到文件管道

详情见[FilePipeline.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/pipeline/FilePipeline.java)

### ResultItemsCollectorPipeline

* 结果收集管道

详情见[ResultItemsCollectorPipeline.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/pipeline/ResultItemsCollectorPipeline.java)

## processor

### PageProcessor

* 用于自定义搜寻器的接口。

* 启动网址和其他设置

* 如何检测获取的网址

* 如何提取和存储数据

详情见[PageProcessor.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/processor/PageProcessor.java)

### SimplePageProcessor

* 实现PageProcessor接口

详情见[SimplePageProcessor.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/processor/SimplePageProcessor.java)

## proxy

### Proxy

* 代理类

详情见[SimplePageProcessor.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/proxy/Proxy.java)

### ProxyProvider

* 代理生成器接口

详情见[ProxyProvider.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/proxy/ProxyProvider.java)

### SimpleProxyProvider

* 代理生成器实现

详情见[SimpleProxyProvider.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/proxy/SimpleProxyProvider.java)

## scheduler

### Scheduler

* URL管理及去重

详情见[Scheduler.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/scheduler/Scheduler.java)

### MonitorableScheduler

* 扩展Scheduler，提供将请求计入调度器功能

详情见[MonitorableScheduler.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/scheduler/MonitorableScheduler.java)

### DuplicateRemovedScheduler

* 删除重复的网址，只推送不重复的网址

详情见[DuplicateRemovedScheduler.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/scheduler/DuplicateRemovedScheduler.java)

### QueueScheduler

* 基本调度程序实现。

* LinkedBlockingQueue存储url并删除HashMap的重复URL。

详情见[DuplicateRemovedScheduler.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/scheduler/QueueScheduler.java)

### PriorityScheduler

* 优先调度器

详情见[PriorityScheduler.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/scheduler/PriorityScheduler.java)

### component

#### DuplitcateRemover

* 请求去重接口

详情见[DuplitcateRemover.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/scheduler/component/DuplitcateRemover.java)

#### HashSetDuplicateRemover

* 请求去重实现

详情见[HashSetDuplicateRemover.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/scheduler/component/HashSetDuplicateRemover.java)

## selector

### Selector

* 抽取器接口

详情见[Selector.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/selector/Selector.java)

### Selectable

* 可选扩展

详情见[Selector.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/selector/Selectable.java)

### AbstractSelectable

* 抽象实现

详情见[AbstractSelectable.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/selector/AbstractSelectable.java)

### AndSelector

* 所有选择器将被安排为管道。

* 下一个选择器使用前一个的结果作为源。

详情见[AndSelector.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/selector/AndSelector.java)

### ElementSelector

* html元素抽取器接口

详情见[ElementSelector.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/selector/ElementSelector.java)

### BaseElementSelector

* ElementSelector抽象实现

详情见[BaseElementSelector.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/selector/BaseElementSelector.java)

### CssSelector

* css抽取器

详情见[CssSelector.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/selector/CssSelector.java)

### HtmlNode

* html节点抽取器

详情见[HtmlNode.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/selector/HtmlNode.java)

### Html

* html抽取器

详情见[Html.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/selector/Html.java)

### PlainText

* 纯文本抽取器

* 无法采取xpth和css抽取器抽取

详情见[PlainText.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/selector/PlainText.java)

### JsonPathSelector

* json path抽取器

详情见[JsonPathSelector.java](../../webmagic-core/src/main/java/us/codecraft/webmagic/selector/JsonPathSelector.java)

### Json