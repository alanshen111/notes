# Internship_01_Kardium

## Takeaways
##### General
- `Map`s can be ordered, it's called a `LinkedHashMap`
- UTF-8 CSV files sometimes come with a byte order marker (BOM), which can make parsing difficult without a library
- `git squash` is a thing
- `git submodule update` and `rebase` and `fetch` can solve many problems
  - `git push origin "branch name" --force-with-lease` can help sometimes too
- "`no upstream`/`detached head`" means the branch can't do much because it doesn't exist on remote yet. You need an initial `push`.
- lambdas can be used to implement single method (functional) interfaces like `Consumer`s
- use brackets to cast properly
  - `(a) b.c.d` casts `a` onto `d`
  - `((a) b).c.d` casts `a` onto `b`
- be very careful on `merge`s - one screw up can fail the whole build, or even worse: **NOT** fail the build

##### Listeners
`Listener`s are great ways to perform an action when something changes. Here is an example of a how to use a listener:

``` Java
public interface ExampleListener<T> {

    void update(T oldValue, T newValue);

}
```

``` Java
public class ExampleClass<T> {

    // ...

    public ExampleClass() {
      // ...
      ExampleListener listener = new ValueListener() {
            @Override
            public void update(Object oldValue, Object newValue) {
                //...
            }
        }
    }

    // ...

    public final void changeSomething() {
        // ...
        listener.update(oldValue, newValue);
    }

}
```

##### Consumers
Similarly to `Listener`s, `Consumer`s can also perform an action the moment an input is provided. Here is an example:

``` Java
public interface Consumer<T> {

    void accept(T value);

}
```

``` Java
public class ExampleClass<T> {

    // ...

    public ExampleClass() {
    // ...
    Consumer<Object> consumer = new Consumer() {
            @Override
            public void accept(Object o) {
                //...
            }
        }
    }

    // ...

    public final void doSomething() {
        // ...
        consumer.accept(value);
    }

}
```

Here is an example of a `Consumer` lambda.
``` Java
Consumer<String> c = (x) -> System.out.println(x.toLowerCase());
c.accept("Qiuqiu")
```

##### Wildcards
`<?>` is a shorthand for` <? extends Object>`, it's also known as an unbounded wildcard. So `List<?>` is a list of anything you want.

Note that the use case is different from `List<Object>`.
``` Java
public void print(List<Object> list); // takes EXACTLY a List<Object> (no subclasses)
```
``` Java
public void print(List<?> list); // takes a List<Object> or its subclasses
```
Theres a lot more to generics... may want to study this more thoroughly...
