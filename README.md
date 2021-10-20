# How to Find and Kill a Port in MacOS

When you see error message: ``` Address already in use - bind ```

Then in terminal run:

```
sudo lsof -i :<port>
```
```
kill -9 <PID>
```

## Example

```
sudo lsof -i :5000

OUTPUT:
COMMAND   PID       USER
Python  64808 danblevins
Python  64809 danblevins
Python  64809 danblevins
```

```
kill -9 64808 && kill -9 64809
```

```
sudo lsof -i :5000

OUTPUT:
null
```

## Inspiration

On occasion, I would run into the "Address already in use - bind" error message and would always have to research the solution, which always took slightly longer than expected. Now, I know exactly where I can look to find the solution.
