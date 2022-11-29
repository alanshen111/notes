# Internship_01_Kardium

## Takeaways
##### General
- `Map`s can be ordered, it's called a `LinkedHashMap`
- UTF-8 CSV files sometimes come with a byte order marker (BOM), which can make parsing difficult without a library
- `git squash` is a thing
- regularly `git submodule update`
- `git push origin "branch name" --force-with-lease` can help sometimes
- lambdas can be used to implement single method interfaces like `Consumer`s

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
    Consumer consumer = new Consumer() {
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
