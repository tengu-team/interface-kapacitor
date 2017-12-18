# Interface Kapacitor

 This is a Juju charm interface layer. This interface is used to
 connect to Kapacitor.

#### Requires

```yaml
requires:
  kapacitor:
    interface: kapacitor
```

```python
@when('kapacitor.available')
def connect_to_kapacitor(kapacitor):
    print(kapacitor.host(), kapacitor.port(), kapacitor.username(), kapacitor.password())
)

```

#### Provides

The Kapacitor charm can be found [here](https://jujucharms.com/u/tengu-team/kapacitor/):

```yaml
provides:
    kapacitor:
      interface: kapacitor
```

```python
@when('layer-kapacitor.started', 'kapacitor.available')
def configure_relation(kapacitor):
    kapacitor.configure(unit_private_ip(), config()['port'])
```


# Contact Information

 - Sébastien Pattyn <sebastien.pattyn@tengu.io>

