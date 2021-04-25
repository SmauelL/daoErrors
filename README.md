# dao 层中当遇到一个 sql.ErrNoRows 的时候，是否应该 Wrap 这个 error，抛给上层。为什么，应该怎么做请写出代码？
> 需要返回，否则只根据错误信息无法快速定位具体错误位置
```
// 返回 code ，发生错误的 sql 语句，与 err 根因
return errors.Wrapf(code, fmt.Sprintf("sql: %s error: %v", sql, err))
```
