Sometimes (i.e. every time) after an update, the controller and the AP won't sync properly and the AP will get stuck in adopting mode. If AP gets stuck in 'adopting' you just need to force it to inform the controller that it's available. Supposedly if you set-inform twice it will 'permanently' fix the issue but I have not had luck with that.

```
$ ssh pconwell@[AP IP address]
$ set-inform http://[ip-of-controller]:8080/inform
```
