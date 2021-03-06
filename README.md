# DropDownList component value change through setState
 
 Need to change the value through setState in change event in which value and dataSource properties are maintain in state.

## Solution

You can change the value through setState method and need to check the condition like e.isInteracted. Please refer the below code.

```
  private contacts: { [key: string]: Object }[] = [
    { displayName: 'bob', id: 'abc' },
    { displayName: 'tom', id: 'efg' }
  ];
  private fields: { [key: string]: Object } = { text: 'displayName', value: 'id' };
  constructor(props: Object) {
    super(props);
    this.onChange = this.onChange.bind(this);
    this.state = { contactId: 'abc', contacts: this.contacts };
  }
  onChange(e: ChangeEventArgs) {
    if (e.isInteracted) {
      this.setState({ contactId: e.value });
    }
  }
  render() {
    return (
      <DropDownListComponent dataSource={this.state.contacts} id="ddlelement" change={this.onChange} value={this.state.contactId} fields={this.fields} />
    );
  }
```

## Installing and Running Application

### Installing

To install all dependent packages, use the below command

```
npm install
```

### Run the application

To compile and run the source files, use the below command

```
npm start
```