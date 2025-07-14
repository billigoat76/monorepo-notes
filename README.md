# monorepo-notes
A beginner-friendly guide to Monorepos
What are monorepos?
# As the name suggests, a single repository (on github lets say) that holds all your frontend, backend, devops code.

Example of monorepos : 
<img width="2452" height="750" alt="image" src="https://github.com/user-attachments/assets/8eb9f028-5024-471c-b67a-9f13929cd269" />

<img width="2512" height="1304" alt="image" src="https://github.com/user-attachments/assets/b6461d1b-0bb2-467d-9d84-407b4e6a9af1" />

Why monorepos ?

Why not Simple folders?
Why cant I just store services (backend, frontend etc) in various top level folders?
You can, and you should if your
1.Services are highly decoupled (dont share any code)
2.Services don’t depend on each other.

For eg - A codebase which has a Golang service and a JS service

<img width="744" height="590" alt="image" src="https://github.com/user-attachments/assets/be3eeed2-8b82-44dd-bb43-e6cf3c2def7d" />

Why monorepos?
    1.Shared Code Reuse
    2.Enhanced Collaboration
    3.Optimized Builds and CI/CD: Tools like TurboRepo offer smart caching and task execution strategies that can significantly reduce build and testing times.
    4.Centralized Tooling and Configuration: Managing build tools, linters, formatters, and other configurations is simpler in a monorepo because you can have a single set of tools for the entire project.
    <img width="2224" height="1596" alt="image" src="https://github.com/user-attachments/assets/fd1b0cec-a1e2-4e09-9160-fe924b719c6c" />


Common monorepo framework in Node.js : 
1 Lerna - https://lerna.js.org/
2 nx - https://github.com/nrwl/nx
3 Turborepo - https://turbo.build/ — Not exactly a monorepo framework
4 Yarn/npm workspaces - https://classic.yarnpkg.com/lang/en/docs/workspaces/

We’ll be going through turborepo since it’s the most relevant one today and provides more things (like build optimisations) that others don’t
<img width="926" height="662" alt="image" src="https://github.com/user-attachments/assets/e2f8e5df-1b1a-4782-9a02-501ced3c450d" />

Before diving deep into the Monorepos,it will help to know what is Build System , Build System Orchestrator and Turborepo!
<img width="1166" height="834" alt="image" src="https://github.com/user-attachments/assets/639f27cb-880c-4842-ade3-42e6a04afaf3" />
Build System
A build system automates the process of transforming source code written by developers into binary code that can be executed by a computer. For JavaScript and TypeScript projects, this process can include transpilation (converting TS to JS), bundling (combining multiple files into fewer files), minification (reducing file size), and more. A build system might also handle running tests, linting, and deploying applications.

Build System Orchestrator
TurboRepo acts more like a build system orchestrator rather than a direct build system itself. It doesn't directly perform tasks like transpilation, bundling, minification, or running tests. Instead, TurboRepo allows you to define tasks in your monorepo that call other tools (which are the actual build systems) to perform these actions. 
These tools can include anything from tsc, vite etc

Monorepo Framework
A monorepo framework provides tools and conventions for managing projects that contain multiple packages or applications within a single repository (monorepo). This includes dependency management between packages, workspace configuration.


Turborepo as a build system orchestrator
Turborepo is a build system orchestrator . 
The key feature of TurboRepo is its ability to manage and optimize the execution of these tasks across your monorepo. It does this through:

    Caching: TurboRepo caches the outputs of tasks, so if you run a task and then run it again without changing any of the inputs (source files, dependencies, configuration), TurboRepo can skip the actual execution and provide the output from the cache. This can significantly speed up build times, especially in continuous integration environments.

    Parallelization: It can run independent tasks in parallel, making efficient use of your machine's resources. This reduces the overall time needed to complete all tasks in your project.

    Dependency Graph Awareness: TurboRepo understands the dependency graph of your monorepo. This means it knows which packages depend on each other and can ensure tasks are run in the correct order.

<img width="1920" height="1106" alt="image" src="https://github.com/user-attachments/assets/8eb8b3ff-79d5-4f24-a6d3-f26c24c11084" />






