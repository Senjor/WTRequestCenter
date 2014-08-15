WTRequestCenter
===============

方便缓存的请求库
无需任何import和配置，目前实现了基础需求
如果有其他需要请在issue 上提出，谢谢！


Convenient cache request library
no any import and Configuration,At present, the foundation needs to achieve is Finised
any question please write at issues ,thank you
使用方法 Usage
===============
#### 注意：所有的请求都是缓存的，POST提供非缓存方式的请求，详情请看Wiki
#### notice:all request is cached ,and the POST request have a request not cached ,please view deatial at Wiki
### GET 请求 GET Request
```objective-c
[WTRequestCenter getWithURL:url
                 parameters:parameters
          completionHandler:^(NSURLResponse *response, NSData *data, NSError *error) {
              id obj = [NSJSONSerialization JSONObjectWithData:data options:NSJSONReadingMutableContainers error:&jsonError];
              NSLog(@"result:%@",obj);
              }
```
              
### POST 请求 POST Request
```objective-c
[WTRequestCenter postWithURL:url
                  parameters:parameters 
           completionHandler:^(NSURLResponse *response, NSData *data, NSError *error) {
                     id obj = [NSJSONSerialization JSONObjectWithData:data options:NSJSONReadingMutableContainers error:&jsonError];
              NSLog(@"result:%@",obj);
               }
```

### 缓存图片  cache image
```objective-c
    NSURL *url = [NSURL URLWithString:@"http://www.xxx.com/eqdsa.jpg"];
    UIImageView *imageView = [[UIImageView alloc] initWithFrame:CGRectZero];
    [WTRequestCenter getImageWithURL:url imageComplectionHandler:^(UIImage *image) {
        imageView.image = image;
    }];
```

### 取消所有请求   Cancel all request
```objective-c
[WTRequestCenter cancelAllRequest];
```

Requirement   需要
===============
Only need iOS 5.0 and later,no more import and Configuration!
仅仅需要iOS5 ！ 不需要其他任何import和配置


## Communication  沟通
- If you **found a bug**, open an issue.
- If you **want to contribute**, submit a pull request.
- If you **have a feature request**, open an issue.
- 如果你**发现bug**,打开右侧的问题
- 如果你**想做出贡献**，提交一个推（pull）的请求
- 如果你**有功能需求**，打开问题

## Communication  UIKit+WTRequestCenter
这里面提供了许多方法
- UIImageView的图片缓存
- UIImage的播放gif+图片缓存
- UIButton的图片缓存
- UIColor的快速创建


