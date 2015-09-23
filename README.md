# generator-mean-seed

[Yeoman](http://yeoman.io) Generator for MEAN-seed - MongoDB, Express.js, AngularJS, Node.js + Yeoman (Grunt, Bower, Yo) + Jasmine, Karma, Protractor (for automated testing)


## Demo & Tests
- [MEAN-seed Website/App after Yeoman build](http://162.243.148.119:3000/)
- [Continuous Integration / Tests](http://162.243.148.119:3010/)
	- This automatically deploys and tests the yeoman generated mean-seed website on each Github push (from local development)
- Test Coverage Reports (currently ~90% frontend coverage, ~60% backend coverage)
	- [Node API/Integration Test Coverage](http://162.243.148.119:3000/src/coverage-node/lcov-report/)
	- [Angular Karma Unit Test Coverage](http://162.243.148.119:3000/src/coverage-angular/PhantomJS%201.9.8%20%28Linux%29/)
- [Backend API Interactive Docs](http://162.243.148.119:3000/api/help)
	- i.e. [Auth API](http://162.243.148.119:3000/api/auth/help)
- [Github Repo with Generated Code](https://github.com/jackrabbitsgroup/mean-seed-gen)


## Learn to Code with MEAN Stack
[Walkthrough course to use this Generator and MEAN stack in general](http://fullstackmean.com/)
	
	
	
## Getting Started

NOTE: This was edited according to steps required to make this work correctly on c9.io IDE. Be sure to use nvm install and nvm use to change your node to the correct version. 

Install Yeoman Yo, Bower, Grunt and other global node modules we'll need, if you don't have them already:
```
$ sudo npm install -g yo bower grunt-cli jasmine-node karma yuidocjs forever less
```

Install this generator:
```
$ npm install -g generator-mean-seed
```

Naviagate to a (new) directory where you want to create your AngularJS and node.js app and initiate the generator then follow the prompts:
```
$ yo mean-seed
```

- NOTE: you can also (first) create a `yo-configs` folder with .json files for the prompts so you don't have to type them all out. This is useful for storing multiple different configurations for different projects - just tell the generator which config to use and you're all set! See the [yo_configs folder](yo-configs) for examples.

- NOTE: if you get errors (i.e. npm or bower install failures or timeouts, which aren't uncommon), just re-run the command `yo mean-seed` OR re-run just the problematic parts, i.e. `bower update && bower install` and/or `npm install`. Once everything has installed properly, just make sure to run grunt: `grunt q`

- NOTE: if you get an EACCESS / permission denied error during the npm install, find the folder that had permissions issues (from the log output) and run `sudo chown -R $USER [path to problematic folder]`.
	- http://foohack.com/2010/08/intro-to-npm/#what_no_sudo

[See here](core-default-node/templates/_README.md) for more/full info and steps.

### Next Steps
- See the generated README.md file in your new mean-seed app!


## Updating
You CAN and SHOULD keep your project up to date with the core (seed) generator you used as it goes through version upgrades. Just re-run:

Ensure the generator is up to date:
```
npm install -g generator-mean-seed
```

Pull in updates to your project (core/seed - make sure to select the same core you used originally). Just type 'a' (for overwrite all) if you get prompted about file conflicts - we'll handle those with Git merge later so it's safe to overwrite everything in the generator branch.
```
yo mean-seed
```

Then if you push, make SURE to ALSO push the/any `yo` branches (i.e. `git push origin yo-core-default`) so other developers get that branch and stay up to date.

See [updating.md](docs/updating.md) for more info.



## (Sub)Generators List

- core-default
- core-scss
- ng-route
- ng-directive
- ng-service
- node-controller

See the [docs/generators](docs/generators) folder for more info.

More generators coming - feel free to create one and submit a pull request!



## Documentation / More Info
See the [generated README.md](core-default-node/templates/_README.md) file and the `docs` folder for all documentation. Each (sub)folder typically has an `overview.md` file - start there. Some key docs (roughly in order of priority) listed below:

- [overview.md](core-default-node/templates/docs/overview.md)
- [setup-running folder](core-default-node/templates/docs/setup-running/)
	- [setup-running/overview.md](core-default-node/templates/docs/setup-running/overview.md)
- [tools-dependencies folder](core-default-node/templates/docs/tools-dependencies/)
- [files folder](core-default-node/templates/docs/files/)
- [testing-automation folder](core-default-node/templates/docs/testing-automation/)
- [frontend-angular/common-actions.md](core-default-node/templates/docs/frontend-angular/common-actions.md)
- [backend-node/common-actions.md](core-default-node/templates/docs/backend-node/common-actions.md)


## Miscellaneous

### What is Yeoman?

If you'd like to get to know Yeoman better and meet some of his friends, [Grunt](http://gruntjs.com) and [Bower](http://bower.io), check out the complete [Getting Started Guide](https://github.com/yeoman/yeoman/wiki/Getting-Started).


### License

[MIT License](http://en.wikipedia.org/wiki/MIT_License)



## Roadmap / To do
See [roadmap.md](docs/roadmap.md)



## Contributing
- while you can fork on Github, we're actually trying a new approach of leveraging Yeoman for different 'core' builds to avoid all the forks. The reason for 'forking' a project is to change it and add functionality that conflicts with or would add too much code bloat to the original repository. However, with Yeoman, we can add EVERYTHING into this ONE project and by using generators, the end user/developer can take ONLY what (s)he wants. So there's no code bloat or worry of this becoming a "kitchen sink" seed with too many features. That's the beauty of Yeoman! So, to contribute, build another subgenerator - either a 'core' generator or a 'module' generator. All the 'core' generators essentially become like the typical 'forks' - a user will decide what core (s)he wants to use and THEN what modules to include with that core.
	- core: see the `core-default` folder/generator for an example
	- module: see the `ng-route` folder/generator for an example
- NOTE: You will still have to fork the project to develop / contribute; but the point is that we should be able to pull-request all forks into the main fork (assuming code quality of course) so shouldn't need any forks that aren't just being used for development. With ONE source of truth and ONE 'production' fork, we should be able to keep everything in sync and up to date rather than changes in one fork not being supported in all other forks.
- NOTE: this is still a new idea/approach to contributing and is a work in progress - suggestions welcome! Or if you just think this is a stupid idea feel free to let us know that too - though constructive criticism is always appreciated ;)
