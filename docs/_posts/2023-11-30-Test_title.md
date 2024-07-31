---
layout: post
title: "Test Title"
description: "Test title description specific to this topic"
date: 2023-11-30
categories: test
---
This is a test post that will be removed once the real blog posts are republished.

In this post we will test the ability to add an image:

JPG Image in special folder: [![Test Image](/assets/posts/delme/test.jpg){: .center }](/assets/posts/delme/test.jpg)

JPG Image in special folder: [![Test Image](/assets/posts/delme/test.jpg){: .center }]

JPG Image in assets folder: [![Test Image](/assets/test2.jpg){: .center }](/assets/test2.jpg)

[![test image](/assets/test2.jpg)]

PNG Image in assets folder: [![Test Image](/assets/test2.png){: .center }](/assets/test2.png)

And we will also test some of the markdown formatting:

# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6

Code view:
```cs
var requestUri = new Uri("http://google.com");
var expectedResponse = "Response text";

var mockResponse = new HttpResponseMessage(HttpStatusCode.OK) { Content = new StringContent(expectedResponse) };
var mockHandler = new Mock<HttpClientHandler>();
mockHandler
    .Protected()
    .Setup<Task<HttpResponseMessage>>(
        "SendAsync",
        It.Is<HttpRequestMessage>(message => message.RequestUri == requestUri),
        It.IsAny<CancellationToken>())
    .Returns(Task.FromResult(mockResponse));

var httpClient = new HttpClient(mockHandler.Object);
var result = await httpClient.GetStringAsync(requestUri).ConfigureAwait(false);
Assert.AreEqual(expectedResponse, result);
```

Link: [Github](https://github.com/dfederm/Testing.HttpClient){:target="_blank"}


