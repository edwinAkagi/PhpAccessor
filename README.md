# PhpAccessor
A elegant accessor hack for PHP after the community failed to pass the motion on a proper getter setter syntax

I know that this is a crazy idea as it is an implemention on PHP instead of in the runtime.

## How does the syntax looks like?
Um..., like this?
### The class with the usage of accessor
```
class Test{

    use Accessor;

    private $aaa = 'rrr';
    private function aaa(){
        return [
            new Get($this, function(){
                return $this->aaa;

        }), new Set($this, function($value){
                $this->aaa = $value;
        })];
    }

}

$test = new Test();
echo $test->aaa;
echo "\n";
$test->aaa = 'ccc';
echo $test->aaa;
```

### The output of the previous code
```
rrr
ccc
```
