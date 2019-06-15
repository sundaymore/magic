# magicexpr

## introduce
magicexpr is an code generation engine for any format code, by using a group of command executor.

## expression 

Actually, an expression in magicexpr is just a command that promise to return a string result. and there is a group of inner engine commands as basic commands, and you can expand the command set if necessary.  

let's see a simple expression: 
```{const helloworld}```    
output: 
```helloworld```  

the word "const" is command name, "helloworld" is first param of "const". the function of const command is just return the first param  

## rule
### three rule
There is three rules that defines the workflow of code generation engine.  
- 1. the code engine can only receive one command as input
- 2. the command contain several params, maybe one? or maybe zero? or maybe more!
- 3. a param can be a string value, also a param can be a command.

### explain

rule 3, for example:  
```{const {const helloworld}}```  
in the above expression ```{const helloworld}``` is a param of the first "const" command although the param itself is as a command.  

we can make it go further, to show a more complex expression:  

```{const {const hello}{const world}} ```  

additionally, if we input expression like  

```{const o}{const k}```  

the engine will wrap the expression with "const" command as  

```{const {const o}{const k}}```  

that is for satisfy the rule 1.    


## how to use

