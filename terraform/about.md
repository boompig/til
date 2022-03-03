[Terraform][1] is a great tool that I've been using to easily deploy and maintain AWS infrastructure.

The commands to create the infrastructure are usually less convoluted than AWS command-line invocation (for example adding tags).

It's also a little easier managing the state of infrastructure: you can use it to import existing configurations and then make little tweaks.

[1]: https://www.terraform.io/

## Tips

You can delete a resource from the state with `tf state rm ...`
