# HOW TO TEST REACT COMPONENTS

### WHAT IS TESTING ?

> Arrang --> Act --> Assert
>
> > Arrange the app in the original state

> > Act is then something happens

> > Assert/ make hypothesis of the new state

Jest is the test runner

```
describe wraps our it or block to group our tests
```

### MATCHERS

```
expect( )
```

return an expectation object

#### Common Matchers

```
.toBe()
.toEqual()
```

#### Truthiness

```
.toBeNull()
.toBeUndefined()
.toBeDefined()
.toBeTruthy()
.toBeFalsy()
```

#### Numbers

```
.toBeGreaterThan()
.toBeGreaterThanOrEqual()
.toBeLessThan()
.toBeLessThanOrEqual()

for floating point equality use .toBeCloseTo()
```

#### Strings

```
.toMatch()
```

#### Array and iterables

```
.toContain()
```

#### Exceptions

```
.toThrow()

the function that throws an exception needs to be invoked within a wrapping function otherwise toThrow assertion will fail

function throwingAnError(){
    throw new Error('Wrong code');
}

test('testing throwing an error function', ()=>{
    expect( ()=> throwingAnError()).toThrow();
})
```

## SNAPSHOT TESTING

```
it('renders correctly enzymes',()=>{
    const wrapper = renders(<Basic />)
    expect(toJson(wrapper)).toMatchSnapshot();
})

```

If you have not ran this command before, a **snapshots** folder and test.js.snap file will be created for you automatically. On every subsequent test the new snapshot will be compared to the existing snapshot file. The test will pass if the snapshot has not changed and fail if it has changed. So essentially snapshot testing allows you to see how your component has changed since the last test, line for line. The lines of code that have changed is known as the diff

to update the snapshot press w and then press u
