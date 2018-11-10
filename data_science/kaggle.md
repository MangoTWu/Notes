# 1. pandas

## 一些使用方法

```python
train['mouyilie']==number
```

返回的是所有数据中该列是否等于该数值的布尔值，True or False

```python
train[train['mouyilie']==number]
```

返回的是满足此列数值等于该指定数的数据行，即完成了筛选

再调用 len() 函数可以完成计数：

```python
len(train[train['mouyilie']==number])
```

