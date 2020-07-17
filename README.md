# 日志

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
