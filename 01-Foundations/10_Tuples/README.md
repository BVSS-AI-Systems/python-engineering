# 🐍 Python Tuples

A **tuple** is an **ordered** collection of items that **cannot be changed** after it is created. It is often called an **immutable list**.

![Python tuple infographic](images/python-tuple.png)

---

## 📖 Topics covered

- Introduction to tuples
- Packing and unpacking
- Accessing items with indexing and slicing
- Why use tuples instead of lists

---

## ⚡ Quick reference

```python
t = ("apple", "banana", "cherry")   # create
single = (5,)                       # single-item tuple needs a comma

t[0]        # 'apple'                 indexing
t[-1]       # 'cherry'                negative indexing
t[0:2]      # ('apple', 'banana')     slicing
t[::-1]     # reversed

packed = 1, 2, 3      # packing
a, b, c = t           # unpacking

len(t)                # 3
t.count("apple")      # 1
t.index("banana")     # 1
"apple" in t          # True
```

---

## ⚖️ Tuple vs list

| | Tuple | List |
|---|---|---|
| Brackets | `( )` | `[ ]` |
| Can change? | ❌ No | ✅ Yes |
| Methods | `count()`, `index()` | `append()`, `remove()`, `sort()`, … |
| Dictionary key? | ✅ Yes | ❌ No |
| Memory | Less | More |
| Use for | Fixed / read-only data | Data that changes |

---

## ✅ Checklist

- [ ] Create a tuple, including a single-item tuple
- [ ] Explain why tuples are immutable
- [ ] Pack and unpack a tuple
- [ ] Access items using positive and negative indexes
- [ ] Slice a tuple with `start:stop:step`
- [ ] Explain when to use a tuple instead of a list
