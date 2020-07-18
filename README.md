# 日志

## 2020年 07月 18日 星期六 17:54:03 CST

date 工具的默认格式受 locale 影响。例如当前主要语言设置的是 C，想要输出简体中文
日期时，首先编辑 /etc/locale.gen，打开 zh_CN.UTF-8 的开关。再运行 locale-gen 工
具，最后用 LANG 环境变量控制 date。

    env LANG=zh_CN.UTF-8 date

## 2020年 07月 17日 星期五 19:54:24 CST

`dev-dependencies` 的依赖不会用在打包中，但会用在功能测试、示例和基准测试里。

```
[dev-dependencies]
tempdir = "0.3"
```

## 2020年 07月 17日 星期五 17:54:14 CST

```
        Vec<T>      &[T]    Box<[T]>
Vec<T>              &x[..]  x.into_boxed_slice()
&[T]    x.to_vec()          Box::new(*x)
Box<T>  x.to_vec()  &*x
```

## 2020年 07月 17日 星期五 16:32:29 CST

```rust
impl<T> Vec<T> {
    /// Shortens the vector, keeping the first len elements and dropping the
    /// rest.
    /// Note that this method has no effect on the allocated capacity of the
    /// vector.
    pub fn truncate(&mut self, len: usize)
}
```

## 2020年 07月 17日 星期五 15:01:11 CST

从 `&[u32]` 中复制最后一个元素，得到 `Option<u32>`。

```rust
fn slice_last(slice: &[u32]) -> Option<u32> {
    slice.last().copied()
}
```

用到的方法是：

```rust
impl<T> for <T> {
    pub fn last(&self) -> Option<&T>
}

impl <'_, T> Option<&'_ T> where T: Copy {
    pub fn copied(self) -> Option<T>
}
```
