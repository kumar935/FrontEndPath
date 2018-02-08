


chrome: 
- works
- text-security disc works

mozilla: 
- doesn't support text-security disc.
- clear password after saving works

safari: 
- supports text-security but still saves password
- clear password after saving doesn't work.
- readonly, then onFocus remove readonly also doesn't work.
- so onFocus remove text-security class thing. this seems to work. Or, keep don't put css in the beginning. put on setTimeout.

IE: 
- doesn't support text-security but still doesn't save password somehow.
