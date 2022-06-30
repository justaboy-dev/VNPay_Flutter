
# VNPAY Flutter Package

## Introduction

This is a package help interactive with VNPAY
## Installation

Add this to you package's pubspec.yaml file:

```bash
  dependencies:
    vnpay_flutter: ^1.0.0
```

Run pub get command

```bash
  flutter pub get
```

## Usage/Examples

```dart
final paymentUrl = VNPAYFlutter.instance.generatePaymentUrl(
      url: 'https://sandbox.vnpayment.vn/paymentv2/vpcpay.html', //vnpay url, default is https://sandbox.vnpayment.vn/paymentv2/vpcpay.html
      version: '2.0.1', //version of VNPAY, default is 2.0.1
      tmnCode: 'XXX', //vnpay tmn code, get from vnpay
      txnRef: DateTime.now().millisecondsSinceEpoch.toString(), //ref code, default is timestamp
      orderInfo: 'Pay 30.000 VND', //order info, default is Pay Order
      amount: 30000, //amount
      returnUrl: 'https://abc.com/return', //https://sandbox.vnpayment.vn/apis/docs/huong-dan-tich-hop/#code-returnurl
      ipAdress: '192.168.10.10', //Your IP address
      vnpayHashKey: 'XXX', //vnpay hash key, get from vnpay
      vnPayHashType: VNPayHashType
          .HMACSHA512, //hash type. Default is HmacSHA512, you can chang it in: https://sandbox.vnpayment.vn/merchantv2
    );
VNPAYFlutter.instance.show(
   paymentUrl: paymentUrl,
   onPaymentSuccess: (params) {}, //on mobile transaction success
   onPaymentError: (params) {}, //on mobile transaction error
   onWebPaymentComplete: (){} //only use in web
);
```
## Authors

- [@justaboy-dev](https://www.github.com/justaboy-dev)