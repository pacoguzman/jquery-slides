!SLIDE

# JavaScript #
# Best Practices #

!SLIDE

# It's still possible to write slow JavaScript on the new, faster JavaScript engines #

### Nicholas Zakas ###

!SLIDE center

# Long-running Javascript #
# = #
# Unresponsive UI #

!SLIDE center

# Long UI updates #
# = #
# Unresponsive UI #

!SLIDE smaller

# minimize number of globals #

    @@@ javascript
    function sum(x, y){
      // antipattern: implied global
      result = x + y;
      return result;
    }

    function sum(x, y){
      var result = x + y;
      return result;
    }

    // follow Single var pattern

!SLIDE bullets

# minimize number of globals #

* Code difficult to read/follow
* Unexpected conflicts

!SLIDE smaller

# Hoisting #

    @@@ javascript
    // antipattern
    myname = "global";
    function func(){
      alert(myname);
      var myname = "local";
      alert(myname);
    }
    func();

!SLIDE smaller

# Hoisting #

    @@@ javascript
    // antipattern
    myname = "global";
    function func(){
      alert(myname); // "undefined"
      var myname = "local";
      alert(myname); // "local"
    }
    func();

    myname = "global";
    function func(){
      var myname;
      alert(myname); // "undefined"
      myname = "local";
      alert(myname); // "local"
    }
    func();

!SLIDE smaller

# (Not) Augmenting Built-in Prototypes #

!SLIDE smaller

# Avoid Implied Typecasting #

    @@@ javascript
    var zero = 0;

    // antipattern
    if (zero == false) {
      // this block is executed
    }

    if (zero === false) {
      // not executed
    }

!SLIDE bullets incremental

# Code conventions #

* indentation
* curly braces
* white spaces
* naming conventions