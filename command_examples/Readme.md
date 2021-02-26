Two files get changed to enable a simple and easy way to view what
the block looks like after it is returned from

### parse_line 

which is defined in examples.rs below.

### nu-command/src/commands.rs

this file has a greatly reduced command set along with

we are able to test only one command at a time.   
in this case we testing the **Append** command.

```rust
fn full_tests() -> Vec<Command> {
    vec![whole_stream_command(Append)]
}

#[test]
fn examples_work_as_expected() -> Result<(), ShellError> {
    for cmd in full_tests() {
        test_examples(cmd)?;
    }

    Ok(())
}
```

### nu-command/src/examples.rs

some debugging println! statements in

```rust
for sample_pipeline in examples {
    let mut ctx = base_context.clone();

    let block = parse_line(sample_pipeline.example, &ctx)?;

    //println!("{:#?}", block);
    println!("\n{:#?}\n", sample_pipeline.example);
    println!("{:?}", block);
```

### To run this code:

```
alias ctnoex='ctno commands::tests::examples_work_as_expected'
```
