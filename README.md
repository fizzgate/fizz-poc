# fizz-poc

fizz-poc是一个被动流量漏洞扫描器，支持XRAY(XPOC)的POC文件，能自动识别.pcap文件的流量漏洞，并生成报告。

## 使用方法
```
Usage: fizz-poc [-hV] [--https] [--cert=<certFile>] [-d=<pocDir>]
                [--key=<keyFile>] [-o=<reportFile>] -p=<pcapFile>
                [--report-format=<reportFormat>] [--threads=<threads>]
                [--timeout=<timeout>]
POC扫描工具
      --cert=<certFile>     SSL证书文件路径
  -d, --poc-dir=<pocDir>    POC目录路径 (可选，默认使用内置POC)
  -h, --help                Show this help message and exit.
      --https               启用HTTPS解密
      --key=<keyFile>       SSL私钥文件路径
  -o, --output=<reportFile> 报告输出文件路径 (默认: poc_report.json)
  -p, --pcap=<pcapFile>     PCAP文件路径
      --report-format=<reportFormat>
                            报告格式 (json/html) (默认: json)
      --threads=<threads>   线程数 (默认: CPU核心数)
      --timeout=<timeout>   超时时间(分钟) (默认: 60)
  -V, --version             Print version information and exit.
```

## 依赖
- JDK 8
- Maven

## 注意

- 如果不指定poc，项目使用内置了pocassist的sqlite数据库
- 被动流量识别停用反连，并且需要再主动确认的流量
- 参数仅供参考，命令只有-d、-p、-o是验证过的

## 示例
```
java -jar  ./fizz-poc-1.0-SNAPSHOT-jar-with-dependencies.jar -d ./poc -p ./pcap_test.pcap
```

## 感谢
- [XRAY](https://github.com/chaitin/xray)
- [pocassist](https://github.com/jweny/pocassist)
