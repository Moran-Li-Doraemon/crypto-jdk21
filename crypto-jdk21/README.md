# crypto-jdk21

JDK 21 版本加密工具包，目录结构与 `crypto-jdk8` 保持一致：

- `com.crypto.gm`：国密算法，包含 `SM2 / SM3 / SM4`
- `com.crypto.aesrsa`：`AES / RSA`
- `com.crypto.other`：`MD5 / SHA / Base64 / Hex / Random / 混淆`
- `com.crypto.demo`：示例入口与烟雾测试

## 构建

```bash
mvn test
mvn package -DskipTests
```

生成文件：

```bash
target/crypto-jdk21-1.0.0.jar
```

## 示例

```java
String key = Sm4Util.generateKey();
String cipher = Sm4Util.encrypt(key, "hello");
String plain = Sm4Util.decrypt(key, cipher);
```

```java
String md5 = HashUtil.md5("hello");
String sha256 = HashUtil.sha256("hello");
```

## 说明

- 需要 JDK 21 编译和运行
- 工具类作者注释统一为 `limoran`
- 依赖 `BouncyCastle`
- `CryptoDemo` 可直接作为快速验证入口
