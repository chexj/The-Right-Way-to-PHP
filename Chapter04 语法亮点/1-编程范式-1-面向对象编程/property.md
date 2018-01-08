Class member variables are called "properties". You may also see them referred to using other terms such as "attributes" or "fields", but for the purposes of this reference we will use "properties". They are defined by using one of the keywords public, protected, or private, followed by a normal variable declaration. This declaration may include an initialization, but this initialization must be a constant value--that is, it must be able to be evaluated at compile time and must not depend on run-time information in order to be evaluated.  

    Note:
    In order to maintain backward compatibility with PHP 4, PHP 5 will still accept the use of the keyword var in property declarations instead of (or in addition to) public, protected, or private. However, var is no longer required. In versions of PHP from 5.0 to 5.1.3, the use of var was considered deprecated and would issue an E_STRICT warning, but since PHP 5.1.3 it is no longer deprecated and does not issue the warning.
    If you declare a property using var instead of one of public, protected, or private, then PHP 5 will treat the property as if it had been declared as public.

Within class methods non-static properties may be accessed by using -> (Object Operator): $this->property (where property is the name of the property). Static properties are accessed by using the :: (Double Colon): self::$property. See Static Keyword for more information on the difference between static and non-static properties.

The pseudo-variable $this is available inside any class method when that method is called from within an object context. $this is a reference to the calling object (usually the object to which the method belongs, but possibly another object, if the method is called statically from the context of a secondary object).  

### Example #1 property declarations

    <?php
    class SimpleClass
    {
    // valid as of PHP 5.6.0:
    public $var1 = 'hello ' . 'world';
    // valid as of PHP 5.3.0:
    public $var2 = <<<EOD
    hello world
    EOD;
    // valid as of PHP 5.6.0:
    public $var3 = 1+2;
    // invalid property declarations:
    public $var4 = self::myStaticMethod();
    public $var5 = $myVar;

    // valid property declarations:
    public $var6 = myConstant;
    public $var7 = array(true, false);

    // valid as of PHP 5.3.0:
    public $var8 = <<<'EOD'
    hello world
    EOD;
    }
    ?>
<br>

    Note:

    There are some nice functions to handle classes and objects. You might want to take a look at the Class/Object Functions.