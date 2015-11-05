# AlipaySDK
AlipaySDK, 3.0.1, iOS, Swift 2, Xcode 7

## Integrate steps
- Copy `AlipaySDK.framework`, `AlipaySDK.bundle`, `libssl.a`, `libcrypto.a` to the `Frameworks` group of your project.
- Copy the `Util` and `openssl` folder into your project's folder and load all the files into the project.
- Copy `Order.h`, `Order.m`, `APAuthV2Info.h`, `APAuthV2Info.m` to the project
- Import the `Order.h`, `<AlipaySDK/AlipaySDK.h>`, `DataSigner.h` in the bridging-header file
## QAs
- add `#import <Foundation/Foundation.h>` the files showing some errors like `NSString` Util/Base64.h Util/openssl_wrapper.h
- disable bitcode in the build setting if error occurs for the libcrypto.a not supporting
- `openssl/asn1.h` file not found, add `$SRCROOT recursive` in the Header Search Paths in Build Settings
- `CFNetwork SSLHandshake failed (-9824)`, 
	`NSURLSession/NSURLConnection HTTP load failed (kCFStreamErrorDomainSSL, -9802)`,
	`[memo: Error Domain=系统繁忙，请稍后再试 Code=1000 "(null)", result: , resultStatus: 4000]`,
	ALI69 网络繁忙，请稍后重试
	enable `Allow Arbitrary Loads` under `App Transport Security Settings` to allow AlipaySDK doing everything it likes(When the fuck will Alipay support https TLS 1.2?)
- ALI69 商户未开通支付宝服务
用户暂未签约？
