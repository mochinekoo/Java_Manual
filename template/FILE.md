# ファイルの書き込み
```java
Path path = null;
try (BufferedWriter write = new BufferedWriter(new OutputStreamWriter(Files.newOutputStream(path), StandardCharsets.UTF_8))) {
  write.write("内容");
}
```

# ファイルのコピー
```
Path path = null;
try (InputStream in = Main.class.getResourceAsStream("/" + type.getName())) {
  Files.copy(in, path);
}
```

# ファイルの読み込み
```java
StringBuilder builder = new StringBuilder();
Path path = null;
try (BufferedReader reader = new BufferedReader(new InputStreamReader(Files.newInputStream(path), StandardCharsets.UTF_8))) {
  String line;
  while((line = reader.readLine()) != null) {
    builder.append(line);
  }
}
```
