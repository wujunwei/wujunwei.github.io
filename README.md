# my blog

### install

---
At first, initialize Hugo modules in your repo. This will create a go.mod file.
```shell
hugo mod init github.com/<your username>/<your repo name>
```

1. Add this theme as your module dependency
   Now, in your config.yaml file, add a module section.

#### Use Hugo modules to add theme
module:
imports:
- path: github.com/hugo-toha/toha/v4
  Check this sample config.yaml for further reference.

2. Update your module
   Now, run this command to load this theme as your module.
```shell
hugo mod tidy
```
Running Locally
Now, you can run your hugo site locally with the following steps:

1. Generate node dependency configuration
   Now run the following command to generate node dependency configuration. This will create the a package.json file in you repo.
```shell
hugo mod npm pack
```
2. Install dependencies
   Install the node dependencies using following command:
```shell
npm install
```
3. Run your site
   Now, run you site locally using following command.
```shell
hugo server -w
```

## todo

- [x] post
- [X] resume
- [ ] comment
- [ ] github workflow