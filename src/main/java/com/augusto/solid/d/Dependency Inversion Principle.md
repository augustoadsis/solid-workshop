#[D]ependecy Inversion Principle (Princípio da inversão de dependências)

* Módulos de alto nível não devem depender de módulos de baixo nível. Ambos devem depender da abstração.
* Abstrações não devem depender de detalhes. Detalhes devem depender de abstrações.

![](./dip.png)

```
public class D_DependencyInversionProblem {

    @AllArgsConstructor
    private static class AuthenticateLogin {

        public boolean login(User user){
            AuthenticationLinkedin authentication = new AuthenticationLinkedin();
            return authentication.login(user);
        }
    }

    private static class AuthenticationLinkedin  {
        public boolean login(User user) {
            //autêntica o login com o Oauth Linkedin.
        }
    }
}
```

```
public class Windows98Machine {

    private final StandardKeyboard keyboard;
    private final Monitor monitor;

    public Windows98Machine() {
        monitor = new Monitor();
        keyboard = new StandardKeyboard();
    }

}

public interface Keyboard { }
public class Windows98Machine{

    private final Keyboard keyboard;
    private final Monitor monitor;

    public Windows98Machine(Keyboard keyboard, Monitor monitor) {
        this.keyboard = keyboard;
        this.monitor = monitor;
    }
}
public class StandardKeyboard implements Keyboard { }
```

### [SOLID Principles: melhorando o design do seu código](https://www.zup.com.br/blog/design-principle-solid)
### [The S.O.L.I.D Principles in Pictures](https://medium.com/backticks-tildes/the-s-o-l-i-d-principles-in-pictures-b34ce2f1e898)
### [A Solid Guide to SOLID Principles](https://www.baeldung.com/solid-principles)

