#[I]nterface Segregation Principle (Princípio segregação de interfaces)

"Make fine grained interfaces that are client specific".
Simplesmente nos incentiva a “fatiar” interfaces “grandes” em interfaces mais granulares. Ter interfaces mais específicas facilita a manutenção e legibilidade do código, além de uma maior coesão.

![](./isp.png)

```
public class I_InterfaceSegregationProblem {
    
    public interface Car {
        void charge();
        void openDoor();
    }

    public static class Fiesta implements Car {
        @Override
        public void charge() {
            throw new UnsupportedOperationException("I'm not an electric car");
        }

        @Override
        public void openDoor() {
            //abrir a porta
        }
    }

    public static class FocusElectric implements Car {
        @Override
        public void charge() {
            //recarregar
        }

        @Override
        public void openDoor() {
            //abrir porta
        }
    }
}
```

```
public interface BearKeeper {
    void washTheBear();
    void feedTheBear();
    void petTheBear();
}

public interface BearCleaner {
    void washTheBear();
}

public interface BearFeeder {
    void feedTheBear();
}

public interface BearPetter {
    void petTheBear();
}

public class BearCarer implements BearCleaner, BearFeeder {

    public void washTheBear() {
        //I think we missed a spot...
    }

    public void feedTheBear() {
        //Tuna Tuesdays...
    }
}

public class CrazyPerson implements BearPetter {

    public void petTheBear() {
        //Good luck with that!
    }
}
```


### [SOLID Principles: melhorando o design do seu código](https://www.zup.com.br/blog/design-principle-solid)
### [The S.O.L.I.D Principles in Pictures](https://medium.com/backticks-tildes/the-s-o-l-i-d-principles-in-pictures-b34ce2f1e898)
### [A Solid Guide to SOLID Principles](https://www.baeldung.com/solid-principles)

