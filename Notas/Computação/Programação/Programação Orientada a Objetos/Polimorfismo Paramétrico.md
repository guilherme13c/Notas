[[Polimorfismo|]][[Introdução a POO|]][[Princípios Da POO|]]
> Java $\implies$ Generics
> C++ $\implies$ Templates
---
# [[Biblioteca STL#Standard Template Library - STL|Templates (C++)]]

```Cpp
template <class T>
T get_max(T a, T b) {
	return (a > b ? a : b);
}

// Função especializada
template <> Interval
get_max<Interval>(Interval a, Interval b) {
	Interval i;
	i.x = a.x > b.x ? a.x : b.x;
	i.y = a.y > b.y ? a.y : b.y;

	return i;
}

int main() {
	int k = get_max<int>(5, 6);              // => 6
	long l = get_max<long>(10, 3);           // => 10
	string str = get_max<string>("ah", "eh") // => "eh"
	return 0;
}
```
---