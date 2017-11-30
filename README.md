# doc
### 流程图
```flow
st=>start: Start
e=>end
op=>operation: My Operation
op2=>operation: My Operation2
cond=>condition: Yes or No?

st->op->op2->cond
cond(yes)->e
cond(no)->op
```