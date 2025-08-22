# camel-jbang-upload-test

Run:

```
camel run upload-test.yaml
```


Try to upload `test.xml`:

```
curl -F "data=@./test.xml" http://0.0.0.0:8080/server/upload
```

Then on the server side I get:

```
2025-08-22 19:06:26.583  INFO 3291 --- [           main] org.apache.camel.main.MainSupport        : Apache Camel (JBang) 4.13.0 is starting
2025-08-22 19:06:26.902  INFO 3291 --- [           main] org.apache.camel.main.MainSupport        : Running Mac OS X 14.7.7 (x86_64)
2025-08-22 19:06:26.903  INFO 3291 --- [           main] org.apache.camel.main.MainSupport        : Using Java 21.0.8 (OpenJDK 64-Bit Server VM) with PID 3291
2025-08-22 19:06:26.903  INFO 3291 --- [           main] org.apache.camel.main.MainSupport        : Started by martin in /Users/martin/Downloads/camel-jbang-upload-test
2025-08-22 19:06:27.148  INFO 3291 --- [           main] org.apache.camel.main.ProfileConfigurer  : The application is starting with profile: dev
2025-08-22 19:06:27.645  INFO 3291 --- [           main] he.camel.cli.connector.LocalCliConnector : Camel JBang CLI enabled
2025-08-22 19:06:27.753  INFO 3291 --- [           main] e.camel.impl.engine.AbstractCamelContext : Apache Camel 4.13.0 (upload-test) is starting
2025-08-22 19:06:28.039  INFO 3291 --- [           main] vertx.core.spi.resolver.ResolverProvider : Using the default address resolver as the dns resolver could not be loaded
2025-08-22 19:06:28.204  INFO 3291 --- [ntloop-thread-0] tform.http.vertx.VertxPlatformHttpServer : Vert.x HttpServer started on 0.0.0.0:8080
2025-08-22 19:06:28.382  INFO 3291 --- [           main] e.camel.impl.engine.AbstractCamelContext : Routes startup (total:1)
2025-08-22 19:06:28.382  INFO 3291 --- [           main] e.camel.impl.engine.AbstractCamelContext :     Started route1 (platform-http:///server/upload)
2025-08-22 19:06:28.383  INFO 3291 --- [           main] e.camel.impl.engine.AbstractCamelContext : Apache Camel 4.13.0 (upload-test) started in 629ms (build:0ms init:0ms start:629ms boot:1s162ms)
2025-08-22 19:06:28.384  INFO 3291 --- [           main] nt.platform.http.main.MainHttpServerUtil : HTTP endpoints summary
2025-08-22 19:06:28.387  INFO 3291 --- [           main] nt.platform.http.main.MainHttpServerUtil :     http://0.0.0.0:8080/server/upload    (POST)   
2025-08-22 19:06:37.259  WARN 3291 --- [ntloop-thread-0] orm.http.vertx.VertxPlatformHttpConsumer : Failed handling platform-http endpoint /server/upload. Caused by: [java.lang.IllegalStateException - Cannot process multipart/form-data requests when useStreaming=true]
java.lang.IllegalStateException: Cannot process multipart/form-data requests when useStreaming=true
	at org.apache.camel.component.platform.http.vertx.StreamingHttpRequestBodyHandler.handle(StreamingHttpRequestBodyHandler.java:52) ~[camel-platform-http-vertx-4.13.0.jar:4.13.0]
	at org.apache.camel.component.platform.http.vertx.VertxPlatformHttpConsumer.populateCamelMessage(VertxPlatformHttpConsumer.java:315) ~[camel-platform-http-vertx-4.13.0.jar:4.13.0]
	at org.apache.camel.component.platform.http.vertx.VertxPlatformHttpConsumer.processHttpRequest(VertxPlatformHttpConsumer.java:309) ~[camel-platform-http-vertx-4.13.0.jar:4.13.0]
	at org.apache.camel.component.platform.http.vertx.VertxPlatformHttpConsumer.handleRequest(VertxPlatformHttpConsumer.java:215) ~[camel-platform-http-vertx-4.13.0.jar:4.13.0]
	at io.vertx.ext.web.impl.RouteState.handleContext(RouteState.java:1283) ~[vertx-web-4.5.16.jar:4.5.16]
	at io.vertx.ext.web.impl.RoutingContextImplBase.iterateNext(RoutingContextImplBase.java:177) ~[vertx-web-4.5.16.jar:4.5.16]
	at io.vertx.ext.web.impl.RoutingContextWrapper.next(RoutingContextWrapper.java:205) ~[vertx-web-4.5.16.jar:4.5.16]
	at io.vertx.ext.web.impl.RouterImpl.handleContext(RouterImpl.java:251) ~[vertx-web-4.5.16.jar:4.5.16]
	at io.vertx.ext.web.impl.RouteState.handleContext(RouteState.java:1283) ~[vertx-web-4.5.16.jar:4.5.16]
	at io.vertx.ext.web.impl.RoutingContextImplBase.iterateNext(RoutingContextImplBase.java:177) ~[vertx-web-4.5.16.jar:4.5.16]
	at io.vertx.ext.web.impl.RoutingContextImpl.next(RoutingContextImpl.java:151) ~[vertx-web-4.5.16.jar:4.5.16]
	at io.vertx.ext.web.impl.RoutingContextImpl.route(RoutingContextImpl.java:100) ~[vertx-web-4.5.16.jar:4.5.16]
	at io.vertx.ext.web.impl.RouterImpl.handle(RouterImpl.java:69) ~[vertx-web-4.5.16.jar:4.5.16]
	at io.vertx.ext.web.impl.RouterImpl.handle(RouterImpl.java:37) ~[vertx-web-4.5.16.jar:4.5.16]
	at io.vertx.core.http.impl.Http1xServerRequestHandler.handle(Http1xServerRequestHandler.java:150) ~[vertx-core-4.5.16.jar:4.5.16]
	at io.vertx.core.http.impl.Http1xServerRequestHandler.handle(Http1xServerRequestHandler.java:42) ~[vertx-core-4.5.16.jar:4.5.16]
	at io.vertx.core.impl.ContextImpl.emit(ContextImpl.java:342) ~[vertx-core-4.5.16.jar:4.5.16]
	at io.vertx.core.impl.DuplicatedContext.emit(DuplicatedContext.java:163) ~[vertx-core-4.5.16.jar:4.5.16]
	at io.vertx.core.http.impl.Http1xServerConnection.handleMessage(Http1xServerConnection.java:174) ~[vertx-core-4.5.16.jar:4.5.16]
	at io.vertx.core.net.impl.ConnectionBase.read(ConnectionBase.java:159) ~[vertx-core-4.5.16.jar:4.5.16]
	at io.vertx.core.net.impl.VertxHandler.channelRead(VertxHandler.java:153) ~[vertx-core-4.5.16.jar:4.5.16]
	at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:442) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:420) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.fireChannelRead(AbstractChannelHandlerContext.java:412) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.ChannelInboundHandlerAdapter.channelRead(ChannelInboundHandlerAdapter.java:93) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.handler.codec.http.websocketx.extensions.WebSocketServerExtensionHandler.onHttpRequestChannelRead(WebSocketServerExtensionHandler.java:158) ~[netty-codec-http-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.handler.codec.http.websocketx.extensions.WebSocketServerExtensionHandler.channelRead(WebSocketServerExtensionHandler.java:82) ~[netty-codec-http-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:442) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:420) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.fireChannelRead(AbstractChannelHandlerContext.java:412) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.vertx.core.http.impl.Http1xUpgradeToH2CHandler.channelRead(Http1xUpgradeToH2CHandler.java:124) ~[vertx-core-4.5.16.jar:4.5.16]
	at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:444) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:420) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.fireChannelRead(AbstractChannelHandlerContext.java:412) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.handler.codec.ByteToMessageDecoder.fireChannelRead(ByteToMessageDecoder.java:346) ~[netty-codec-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.handler.codec.ByteToMessageDecoder.fireChannelRead(ByteToMessageDecoder.java:333) ~[netty-codec-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.handler.codec.ByteToMessageDecoder.callDecode(ByteToMessageDecoder.java:455) ~[netty-codec-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.handler.codec.ByteToMessageDecoder.channelRead(ByteToMessageDecoder.java:290) ~[netty-codec-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:444) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:420) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.fireChannelRead(AbstractChannelHandlerContext.java:412) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.vertx.core.http.impl.Http1xOrH2CHandler.end(Http1xOrH2CHandler.java:61) ~[vertx-core-4.5.16.jar:4.5.16]
	at io.vertx.core.http.impl.Http1xOrH2CHandler.channelRead(Http1xOrH2CHandler.java:38) ~[vertx-core-4.5.16.jar:4.5.16]
	at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:444) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:420) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.fireChannelRead(AbstractChannelHandlerContext.java:412) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.DefaultChannelPipeline$HeadContext.channelRead(DefaultChannelPipeline.java:1357) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:440) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:420) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.DefaultChannelPipeline.fireChannelRead(DefaultChannelPipeline.java:868) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.nio.AbstractNioByteChannel$NioByteUnsafe.read(AbstractNioByteChannel.java:166) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.nio.NioEventLoop.processSelectedKey(NioEventLoop.java:796) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.nio.NioEventLoop.processSelectedKeysOptimized(NioEventLoop.java:732) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.nio.NioEventLoop.processSelectedKeys(NioEventLoop.java:658) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.nio.NioEventLoop.run(NioEventLoop.java:562) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.util.concurrent.SingleThreadEventExecutor$4.run(SingleThreadEventExecutor.java:998) ~[netty-common-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.util.internal.ThreadExecutorMap$2.run(ThreadExecutorMap.java:74) ~[netty-common-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.util.concurrent.FastThreadLocalRunnable.run(FastThreadLocalRunnable.java:30) ~[netty-common-4.1.119.Final.jar:4.1.119.Final]
	at java.base/java.lang.Thread.run(Thread.java:1583) [?:?]
2025-08-22 19:06:37.268 ERROR 3291 --- [ntloop-thread-0] io.vertx.ext.web.RoutingContext          : Unhandled exception in router
java.lang.IllegalStateException: Cannot process multipart/form-data requests when useStreaming=true
	at org.apache.camel.component.platform.http.vertx.StreamingHttpRequestBodyHandler.handle(StreamingHttpRequestBodyHandler.java:52) ~[camel-platform-http-vertx-4.13.0.jar:4.13.0]
	at org.apache.camel.component.platform.http.vertx.VertxPlatformHttpConsumer.populateCamelMessage(VertxPlatformHttpConsumer.java:315) ~[camel-platform-http-vertx-4.13.0.jar:4.13.0]
	at org.apache.camel.component.platform.http.vertx.VertxPlatformHttpConsumer.processHttpRequest(VertxPlatformHttpConsumer.java:309) ~[camel-platform-http-vertx-4.13.0.jar:4.13.0]
	at org.apache.camel.component.platform.http.vertx.VertxPlatformHttpConsumer.handleRequest(VertxPlatformHttpConsumer.java:215) ~[camel-platform-http-vertx-4.13.0.jar:4.13.0]
	at io.vertx.ext.web.impl.RouteState.handleContext(RouteState.java:1283) ~[vertx-web-4.5.16.jar:4.5.16]
	at io.vertx.ext.web.impl.RoutingContextImplBase.iterateNext(RoutingContextImplBase.java:177) ~[vertx-web-4.5.16.jar:4.5.16]
	at io.vertx.ext.web.impl.RoutingContextWrapper.next(RoutingContextWrapper.java:205) ~[vertx-web-4.5.16.jar:4.5.16]
	at io.vertx.ext.web.impl.RouterImpl.handleContext(RouterImpl.java:251) ~[vertx-web-4.5.16.jar:4.5.16]
	at io.vertx.ext.web.impl.RouteState.handleContext(RouteState.java:1283) ~[vertx-web-4.5.16.jar:4.5.16]
	at io.vertx.ext.web.impl.RoutingContextImplBase.iterateNext(RoutingContextImplBase.java:177) ~[vertx-web-4.5.16.jar:4.5.16]
	at io.vertx.ext.web.impl.RoutingContextImpl.next(RoutingContextImpl.java:151) ~[vertx-web-4.5.16.jar:4.5.16]
	at io.vertx.ext.web.impl.RoutingContextImpl.route(RoutingContextImpl.java:100) ~[vertx-web-4.5.16.jar:4.5.16]
	at io.vertx.ext.web.impl.RouterImpl.handle(RouterImpl.java:69) ~[vertx-web-4.5.16.jar:4.5.16]
	at io.vertx.ext.web.impl.RouterImpl.handle(RouterImpl.java:37) ~[vertx-web-4.5.16.jar:4.5.16]
	at io.vertx.core.http.impl.Http1xServerRequestHandler.handle(Http1xServerRequestHandler.java:150) ~[vertx-core-4.5.16.jar:4.5.16]
	at io.vertx.core.http.impl.Http1xServerRequestHandler.handle(Http1xServerRequestHandler.java:42) ~[vertx-core-4.5.16.jar:4.5.16]
	at io.vertx.core.impl.ContextImpl.emit(ContextImpl.java:342) ~[vertx-core-4.5.16.jar:4.5.16]
	at io.vertx.core.impl.DuplicatedContext.emit(DuplicatedContext.java:163) ~[vertx-core-4.5.16.jar:4.5.16]
	at io.vertx.core.http.impl.Http1xServerConnection.handleMessage(Http1xServerConnection.java:174) ~[vertx-core-4.5.16.jar:4.5.16]
	at io.vertx.core.net.impl.ConnectionBase.read(ConnectionBase.java:159) ~[vertx-core-4.5.16.jar:4.5.16]
	at io.vertx.core.net.impl.VertxHandler.channelRead(VertxHandler.java:153) ~[vertx-core-4.5.16.jar:4.5.16]
	at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:442) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:420) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.fireChannelRead(AbstractChannelHandlerContext.java:412) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.ChannelInboundHandlerAdapter.channelRead(ChannelInboundHandlerAdapter.java:93) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.handler.codec.http.websocketx.extensions.WebSocketServerExtensionHandler.onHttpRequestChannelRead(WebSocketServerExtensionHandler.java:158) ~[netty-codec-http-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.handler.codec.http.websocketx.extensions.WebSocketServerExtensionHandler.channelRead(WebSocketServerExtensionHandler.java:82) ~[netty-codec-http-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:442) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:420) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.fireChannelRead(AbstractChannelHandlerContext.java:412) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.vertx.core.http.impl.Http1xUpgradeToH2CHandler.channelRead(Http1xUpgradeToH2CHandler.java:124) ~[vertx-core-4.5.16.jar:4.5.16]
	at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:444) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:420) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.fireChannelRead(AbstractChannelHandlerContext.java:412) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.handler.codec.ByteToMessageDecoder.fireChannelRead(ByteToMessageDecoder.java:346) ~[netty-codec-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.handler.codec.ByteToMessageDecoder.fireChannelRead(ByteToMessageDecoder.java:333) ~[netty-codec-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.handler.codec.ByteToMessageDecoder.callDecode(ByteToMessageDecoder.java:455) ~[netty-codec-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.handler.codec.ByteToMessageDecoder.channelRead(ByteToMessageDecoder.java:290) ~[netty-codec-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:444) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:420) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.fireChannelRead(AbstractChannelHandlerContext.java:412) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.vertx.core.http.impl.Http1xOrH2CHandler.end(Http1xOrH2CHandler.java:61) ~[vertx-core-4.5.16.jar:4.5.16]
	at io.vertx.core.http.impl.Http1xOrH2CHandler.channelRead(Http1xOrH2CHandler.java:38) ~[vertx-core-4.5.16.jar:4.5.16]
	at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:444) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:420) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.fireChannelRead(AbstractChannelHandlerContext.java:412) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.DefaultChannelPipeline$HeadContext.channelRead(DefaultChannelPipeline.java:1357) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:440) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:420) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.DefaultChannelPipeline.fireChannelRead(DefaultChannelPipeline.java:868) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.nio.AbstractNioByteChannel$NioByteUnsafe.read(AbstractNioByteChannel.java:166) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.nio.NioEventLoop.processSelectedKey(NioEventLoop.java:796) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.nio.NioEventLoop.processSelectedKeysOptimized(NioEventLoop.java:732) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.nio.NioEventLoop.processSelectedKeys(NioEventLoop.java:658) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.channel.nio.NioEventLoop.run(NioEventLoop.java:562) ~[netty-transport-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.util.concurrent.SingleThreadEventExecutor$4.run(SingleThreadEventExecutor.java:998) ~[netty-common-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.util.internal.ThreadExecutorMap$2.run(ThreadExecutorMap.java:74) ~[netty-common-4.1.119.Final.jar:4.1.119.Final]
	at io.netty.util.concurrent.FastThreadLocalRunnable.run(FastThreadLocalRunnable.java:30) ~[netty-common-4.1.119.Final.jar:4.1.119.Final]
	at java.base/java.lang.Thread.run(Thread.java:1583) [?:?]
```