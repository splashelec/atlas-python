# *Python* version of the *Atlas* toolkit

[![Run on Repl.it](https://repl.it/badge/github/epeios-q37/atlas-python)](https://q37.info/s/vwpsw73v)  
[![Version 0.12](https://img.shields.io/static/v1.svg?&color=90b4ed&label=Version&message=0.12&style=for-the-badge)](http://github.com/epeios-q37/atlas-python/)
[![Stars](https://img.shields.io/github/stars/epeios-q37/atlas-python.svg?style=for-the-badge)](https://github.com/epeios-q37/atlas-python/stargazers)
[![Forks](https://img.shields.io/github/forks/epeios-q37/atlas-python.svg?style=for-the-badge)](https://github.com/epeios-q37/atlas-python/stargazers)
[![license: MIT](https://img.shields.io/github/license/epeios-q37/atlas-python?color=yellow&style=for-the-badge)](https://github.com/epeios-q37/atlas-python/blob/master/LICENSE)
[![Documentation](https://img.shields.io/static/v1?label=documentation&message=atlastk.org&color=ff69b4&style=for-the-badge)](https://atlastk.org)

[![Version](https://img.shields.io/pypi/v/atlastk?style=for-the-badge&color=90b4ed&label=PyPi)![Download stats](https://img.shields.io/pypi/dm/atlastk.svg?style=for-the-badge)](http://q37.info/s/9srmskcm)

> The [*Atlas* toolkit](https://atlastk.org) is available for:
> 
> | Language | *GitHub* repository| Online démonstrations | Stars 
> |-|-|-|-|
> | [*Java*](https://q37.info/s/qtnkp9w4) |<https://github.com/epeios-q37/atlas-java> | <https://q37.info/s/3vwk3h3n> | [![Stars](https://img.shields.io/github/stars/epeios-q37/atlas-java.svg?style=social)](https://github.com/epeios-q37/atlas-java/stargazers) |
> | [*Node.js*](https://q37.info/s/3d7hr733) | <https://github.com/epeios-q37/atlas-node> | <https://q37.info/s/st7gccd4> | [![Stars](https://img.shields.io/github/stars/epeios-q37/atlas-node.svg?style=social)](https://github.com/epeios-q37/atlas-node/stargazers) |
> | [*Perl*](https://q37.info/s/4nvmwjgg) |<https://github.com/epeios-q37/atlas-perl> | <https://q37.info/s/h3h34zgq> | [![Stars](https://img.shields.io/github/stars/epeios-q37/atlas-perl.svg?style=social)](https://github.com/epeios-q37/atlas-perl/stargazers) |
> | [*Python*](https://q37.info/s/pd7j9k4r) | <https://github.com/epeios-q37/atlas-python> | <https://q37.info/s/vwpsw73v> | [![Stars](https://img.shields.io/github/stars/epeios-q37/atlas-python.svg?style=social)](https://github.com/epeios-q37/atlas-python/stargazers) |
> | [*Ruby*](https://q37.info/s/gkfj3zpz) | <https://github.com/epeios-q37/atlas-ruby> | <https://q37.info/s/9thdtmjg> | [![Stars](https://img.shields.io/github/stars/epeios-q37/atlas-ruby.svg?style=social)](https://github.com/epeios-q37/atlas-ruby/stargazers) |

---

***Note for Repl.it users (online demonstrations)***: **after having launched a demonstration, you may have to click the refresh button (red arrow on picture below) top left in the frame containing the QR code to display it for the other demonstrations.**

[![The refresh button](https://q37.info/s/vsc3c7gc.png "The button to click to display the QR code")](http://q37.info/s/zbgfjtp9)

---

**If you are looking for the *WebGPIO* application, an application with which you can control the Raspberry Pi (or other similar devices) GPIO with your smartphone, you will find it at the bottom of this page, in the *Raspberry Pi*/*ODROID-C2* section.**


---

## Straight to the point: the [*Hello, World!*](https://en.wikipedia.org/wiki/%22Hello,_World!%22_program) program

### Source code

```python
import atlastk as Atlas

body = """
<div style="display: table; margin: 50px auto auto auto;">
 <fieldset>
  <input id="input" maxlength="20" placeholder="Enter a name here" type="text"
         data-xdh-onevent="Submit" value="World"/>
  <div style="display: flex; justify-content: space-around; margin: 5px auto auto auto;">
   <button data-xdh-onevent="Submit">Submit</button>
   <button data-xdh-onevent="Clear">Clear</button>
  </div>
 </fieldset>
</div>
"""

def ac_connect(dom):
  dom.inner("", body)
  dom.focus("input")

def ac_submit(dom):
  dom.alert("Hello, " + dom.get_content("input") + "!")
  dom.focus("input")

def ac_clear(dom):
  if ( dom.confirm("Are you sure?") ):
    dom.set_content("input", "")
  dom.focus("input")

callbacks = {
  "": ac_connect,  # The action label for a new connection is an empty string.
  "Submit": ac_submit,
  "Clear": ac_clear,
}

Atlas.launch(callbacks)
```


### Result

[![Little demonstration](https://q37.info/download/assets/Hello.gif "A basic example")](https://q37.info/s/vwpsw73v)

### Too good to be true? Try it now - it's quick and easy!

#### Online, with nothing to install

Thanks to [Replit](https://q37.info/s/mxmgq3qm), an [online IDE](https://q37.info/s/zzkzbdw7), you can write and run programs using the *Atlas* toolkit directly in your web browser, without having to install *Python* on your computer.

To see some examples, like the following [*TodoMVC*](http://todomvc.com/) application or the above [*Hello, World!*](https://en.wikipedia.org/wiki/%22Hello,_World!%22_program) program, simply:
- go [here](https://q37.info/s/vwpsw73v) (also accessible with the [![Run on Repl.it](https://repl.it/badge/github/epeios-q37/atlas-python)](https://q37.info/s/vwpsw73v) badge on the top of this page),
-  click on the green `run` button,
-  select the demonstration you want to see,
-  click (or scan with your smartphone) the then displayed [QR code](https://q37.info/s/3pktvrj7),
- … and, as you wish, run your own tests directly in your web browser, by modifying the code of the examples or by writing your own code.

[![TodoMVC](https://q37.info/download/TodoMVC.gif "The TodoMVC application made with the Atlas toolkit")](https://q37.info/s/vwpsw73v)

#### With *Python* on your computer

```
git clone http://github.com/epeios-q37/atlas-python
cd atlas-python/examples
python Hello/
```

## Your turn

If you want to take your code to the next level, from [CLI](https://q37.info/s/cnh9nrw9) to [GUI](https://q37.info/s/hw9n3pjs), then you found the right toolkit.

With the [*Atlas* toolkit](http://atlastk.org/), you transform your programs in modern web applications ([*SPA*](https://q37.info/s/7sbmxd3j)), but without the usual hassles:
- no *JavaScript* to write; only *HTML*(/*CSS*) and *Python*,
- no [front and back end architecture](https://q37.info/s/px7hhztd) to bother with,
- no [web server](https://q37.info/s/n3hpwsht) (*Apache*, *Nginx*…) to install,
- no need to deploy your application on a remote server,
- no incoming port to open on your internet box or routeur.

The *Atlas* toolkit is written in pure *Python*, with no native code and no dependencies, allowing the *Atlas* toolkit to be used on all environments where *Python* is available. 

And, icing on the cake, simply by running them on a local computer with a simple internet connexion, applications using the *Atlas* toolkit will be accessible from the entire internet on laptops, smartphones, tablets…

The *Atlas* toolkit is particularly well suited for educational purposes, to write modern programming exercises, i.e. with a true graphical interface instead of the usual outdated textual one. More about this can be found [here](https://q37.info/s/cbms43s9).

There is also a stub to for this library at address <https://q37.info/s/zzcn3wnx>.

## Content of the repository

The `atlastk` directory contains the *Python* source code of the *Atlas* toolkit, which is the directory you have to reference in `PYTHONPATH` in order to use the *Atlas* toolkit in your own program, unless you have installed the [*atlastk* package](http://q37.info/s/9srmskcm) with `pip install atlastk`.

In the `examples` directory, you will found following examples:

- `Blank`: very basic example,
- `Hello`: ["*Hello, World!*"](https://en.wikipedia.org/wiki/%22Hello,_World!%22_program),
- `Chatroom`: multi-user chatroom,
- `ReversiTXT`: [*Reversi game*](http://q37.info/s/zz3dzmf7) with `X` and `O` for token,
- `Notes`: note taking program,
- `TodoMVC`: [*TodoMVC*](http://todomvc.com/),
- `Hangman`: [Hangman game](http://q37.info/s/gtdtk4hp),
- `15-puzzle`: [*15-puzzle* game](https://q37.info/s/jn9zg3bn),
- `ReversiIMG`: [*Reversi game*](http://q37.info/s/zz3dzmf7) with more evolved graphics,
- `ReversiXSL`: [*Reversi game*](http://q37.info/s/zz3dzmf7) using *XSL*.

Other examples are detailed in the next section.

Except for the *ErgoJr*, *GPIO* and *RGB* applications, which are detailed in the next section, to run an example, launch, from within the repository, `python main.py`, and select the example you want to run.  
You can also directly launch, from within the `examples` directory, `python <Name>/` (don't forget the final `/`), where `<Name>` is the name of the example (`Blank`, `Chatroom`…).

The *Stars* application is an example where the *Atlas* *toolkit* is used to control a [*Pygame*](https://en.wikipedia.org/wiki/Pygame) based application. Of course, *Pygame* needs to be installed.

## *Raspberry Pi*/*ODROID-C2*

**If the applications does not work on your *Raspberry Pi*, please see this issue: <https://github.com/epeios-q37/atlas-python/issues/1>**

The *GPIO* and *RGB* applications are designed to be used on a *Raspberry Pi* or a *ODROID-C2*.

For the *Raspberry Pi*, the `RPi.GPIO` *Python* module have to be installed (this is probably already the case).


For the *ODROID-C2*, The *Python* version of *WiringPi* must be installed, and the application has to be launched, from within the `examples` directory, with `sudo` (`sudo python GPIO/` or `sudo python RGB/`).


The *ErgoJr* application is experimental and to control a *Poppy* *Ergo Jr* robot.

The *RGB* application is dedicated to the control of a RGB led, and the *GPIO* (aka *WebGPIO*) application allows to control the basic pins. Here is a video to see how they work:

[![RGB video](https://img.youtube.com/vi/C4p2iX6gc-Q/0.jpg)](https://www.youtube.com/watch?v=C4p2iX6gc-Q)

Same video on [*PeerTube*](https://en.wikipedia.org/wiki/PeerTube) : <https://peertube.video/videos/watch/e7e02356-c9c3-4590-8ec0-8f8da06ff312>


