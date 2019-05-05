# What's new in Python 3.8

---

### About me 

* Backend engineer using Python and Django.
* Part of triager team.
* Contributed around 30 patches upstream from July 2018.
* Primarily interested in unittest.mock and security.

---

### New features in 3.8

* [Assignment expressions](https://github.com/python/cpython/pull/10497)
* [Syntax for positional only arguments](https://github.com/python/cpython/pull/12701)
* [multiprocessing.shared_memory](https://github.com/python/cpython/pull/11664)

----

### Assignment expressions (PEP 572)

* Assignment operation can now be used as an expression using the walrus operator :=
* Works with conditional clauses, list comprehensions, etc.
* Top level assignment needs paranthesis.

```
name = person.get("name")
if name:
    print(f"Hello, {name}")
```

```
if name := person.get("name"):
    print(f"Hello, {name}")
```

----

### Syntax for positional only arguments (PEP 570)

* Arguments preceding / are now treated as positional only arguments.

```
def process_data(data, /, clean=True):
    pass

process_data(data="foo") # error
process_data("foo") # works
```

---

### multiprocessing.shared_memory

* Provides shared memory for direct access across processes.
* Supports numpy out of the box.

---

### Optimisations in Python 3.8

---

### Argument clinic optimizations

* Optimisations made to argument clinic for parsing functions with positional only arguments and keyword arguments. [bpo 35582](https://bugs.python.org/issue35582)
* Made functions like str.replace, getattr, etc. arounf 30% faster.
* dict.pop is now 35% faster. [bpo 20180](https://bugs.python.org/issue20180)

---

### miscellaneous optimizations

* namedtuple attribute access is now around 2x faster. [bpo 32492](bugs.python.org/issue32492)
* IPAddress checks in large networks is around 3x faster [bpo 25430](https://bugs.python.org/issue25430)

---

### Python 2 EoL

* No bug fixes.
* No security updates. CVE vulnerabilities needs to be patched by vendors providing commercial support.
* No optimizations were backported to 2.7.
* Support from core team ends with January 2020.

---

### Support CPython development.

* Everything is done on volunteer time with no corporation.
* #3 popular language only few people work on CPython full time.
* Organizations can help in donating money or volunteer work.
* Contributions not only come in code. Documentation, testing, triaging, discussions etc. are all important.