## CLI errors

_note:_ `alias npx='dx'` is in `${HOME}/.bashrc` but still `executeCommand` code does not work.

```sh
$ deno run -A npm:storybook@latest init
error: Uncaught (in promise) ExecaError: Command failed with ENOENT: npx --yes 'create-storybook@10.3.5'
spawn npx ENOENT
  return new ErrorClass(message, options);
         ^
    at getFinalError (file:///workspaces/glowing-disco/node_modules/.deno/storybook@10.3.5/node_modules/storybook/dist/_node-chunks/chunk-GOY6UMCB.js:13112:10)
    at makeError (file:///workspaces/glowing-disco/node_modules/.deno/storybook@10.3.5/node_modules/storybook/dist/_node-chunks/chunk-GOY6UMCB.js:14648:15)
    at getAsyncResult (file:///workspaces/glowing-disco/node_modules/.deno/storybook@10.3.5/node_modules/storybook/dist/_node-chunks/chunk-GOY6UMCB.js:17294:158)
    at handlePromise (file:///workspaces/glowing-disco/node_modules/.deno/storybook@10.3.5/node_modules/storybook/dist/_node-chunks/chunk-GOY6UMCB.js:17280:162)
    at processTicksAndRejections (ext:core/01_core.js:400:7)
    at drainTicks (ext:core/01_core.js:427:5)
Caused by: Error: spawn npx ENOENT
    at __node_internal_errnoException (ext:deno_node/internal/errors.ts:137:14)
    at _createSpawnError (ext:deno_node/internal/child_process.ts:1150:17)
    at ChildProcess.#spawnInternal (ext:deno_node/internal/child_process.ts:349:13)
    at ChildProcess.spawn (ext:deno_node/internal/child_process.ts:154:24)
    at spawn (node:child_process:151:9)
    at spawnSubprocessAsync (file:///workspaces/glowing-disco/node_modules/.deno/storybook@10.3.5/node_modules/storybook/dist/_node-chunks/chunk-GOY6UMCB.js:17224:18)
    at execaCoreAsync (file:///workspaces/glowing-disco/node_modules/.deno/storybook@10.3.5/node_modules/storybook/dist/_node-chunks/chunk-GOY6UMCB.js:17189:204)
    at callBoundExeca (file:///workspaces/glowing-disco/node_modules/.deno/storybook@10.3.5/node_modules/storybook/dist/_node-chunks/chunk-GOY6UMCB.js:17352:68)
    at boundExeca (file:///workspaces/glowing-disco/node_modules/.deno/storybook@10.3.5/node_modules/storybook/dist/_node-chunks/chunk-GOY6UMCB.js:17334:180)
    at executeCommand (file:///workspaces/glowing-disco/node_modules/.deno/storybook@10.3.5/node_modules/storybook/dist/_node-chunks/chunk-GOY6UMCB.js:17431:22)
```

_note:_ calling explicitly in bash where `alias npx='dx'` from `${HOME}/.bashrc` works to get around `ExecaError: Command failed with ENOENT: npx --yes 'create-storybook@10.3.5' spawn npx ENOENT`; however code still does not work.

```sh
$ npx --yes 'create-storybook@10.3.5'
│
■  Error: Unable to find a usable package manager within NPM, PNPM, Yarn and Yarn 2
│  at JsPackageManagerFactory.getPackageManagerType
│  (file:///home/vscode/.cache/deno/deno_x_cache/npm-create-storybook@10.3.5/node_modules/.deno/storybook@10.3.5/node_modules/storybook/dist/_node-chunks/chunk-GOY6UMCB.js:18444:11)
│  at PreflightCheckCommand.execute
│  (file:///home/vscode/.cache/deno/deno_x_cache/npm-create-storybook@10.3.5/node_modules/.deno/create-storybook@10.3.5/node_modules/create-storybook/dist/_node-chunks/chunk-5VDIKOHD.js:548:125)
│  at executePreflightCheck
│  (file:///home/vscode/.cache/deno/deno_x_cache/npm-create-storybook@10.3.5/node_modules/.deno/create-storybook@10.3.5/node_modules/create-storybook/dist/_node-chunks/chunk-5VDIKOHD.js:569:75)
│  at doInitiate
│  (file:///home/vscode/.cache/deno/deno_x_cache/npm-create-storybook@10.3.5/node_modules/.deno/create-storybook@10.3.5/node_modules/create-storybook/dist/_node-chunks/chunk-5VDIKOHD.js:2876:83)
│  at
│  file:///home/vscode/.cache/deno/deno_x_cache/npm-create-storybook@10.3.5/node_modules/.deno/create-storybook@10.3.5/node_modules/create-storybook/dist/_node-chunks/chunk-5VDIKOHD.js:2928:26
│  at withTelemetry
│  (file:///home/vscode/.cache/deno/deno_x_cache/npm-create-storybook@10.3.5/node_modules/.deno/storybook@10.3.5/node_modules/storybook/dist/_node-chunks/chunk-FIR43JGQ.js:225:18)
│  at initiate
│  (file:///home/vscode/.cache/deno/deno_x_cache/npm-create-storybook@10.3.5/node_modules/.deno/create-storybook@10.3.5/node_modules/create-storybook/dist/_node-chunks/chunk-5VDIKOHD.js:2921:30)
│  at _Command.<anonymous>
│  (file:///home/vscode/.cache/deno/deno_x_cache/npm-create-storybook@10.3.5/node_modules/.deno/create-storybook@10.3.5/node_modules/create-storybook/dist/_node-chunks/run-U7WRX526.js:2684:150)
│  at _Command.listener [as _actionHandler]
│  (file:///home/vscode/.cache/deno/deno_x_cache/npm-create-storybook@10.3.5/node_modules/.deno/create-storybook@10.3.5/node_modules/create-storybook/dist/_node-chunks/run-U7WRX526.js:1226:161)
│  at
│  file:///home/vscode/.cache/deno/deno_x_cache/npm-create-storybook@10.3.5/node_modules/.deno/create-storybook@10.3.5/node_modules/create-storybook/dist/_node-chunks/run-U7WRX526.js:1889:24
```

## GitHub Chat

https://github.com/storybookjs/storybook/blob/ff98f860a1cd8f80c40c0e0f8e8dd39944dfed05/code/core/src/common/js-package-manager/JsPackageManagerFactory.ts#L48-L123

To “support Deno” for Storybook (as requested in storybookjs/storybook/discussions/29360 and tracked via denoland/deno/issues/20610), you need **two layers**:

1) **Make Storybook’s CLI able to run when the host runtime is Deno** (even if the project still uses npm packages).
2) **Make Storybook’s “project + package manager” assumptions tolerant of Deno’s npm-compat environment** (and, ideally, Fresh/Deno-centric workflows).

Below is what’s concretely needed, mapped to the current Storybook package-manager detection you showed.

---

## 1) Decide the support target (minimum viable vs “native Deno”)

There are three realistic “levels” of Deno support:

### Level A (MVP): “Deno as the process runner, npm packages underneath”
Goal commands (from the discussion):
- `deno run -A npm:storybook@latest init`
- `deno task storybook`

This still uses npm-compat to load Node packages. You’re not rewriting Storybook for Deno; you’re making the CLI **not break** when `process` / lockfiles / user-agent / PATH behave differently.

### Level B: “Deno projects (Fresh) can use Storybook with a Node toolchain for installs”
Storybook is executed with Node (or via `deno run npm:...`), but the project might not have `package-lock.json` / `yarn.lock` / `pnpm-lock.yaml` at all, and may use `deno.json` / `deno.lock`.

### Level C: “Fully native Deno”
Very large scope: replace Node APIs, bundler integrations, addon ecosystem expectations, etc. Not what those threads are asking for.

Most likely you want **Level A + a bit of Level B**.

---

## 2) Fix package manager detection for Deno environments (your snippet)

Today Storybook decides a package manager using:

- closest lockfile (yarn/pnpm/npm/bun)
- then “user agent” inference
- fallback to npm if `hasNPM(cwd)` is true
- else throw

In a Deno world:
- a repo may have **no npm/yarn/pnpm lockfile** (Fresh / Deno-first)
- Deno has its own signals: `deno.json`, `deno.jsonc`, `deno.lock`
- the “right” installer might still be **npm**, but the **runner** is **deno**
- invoking `npx`/`pnpx` isn’t how you run things; it’s `deno run npm:...`

### Concretely needed changes
1) **Introduce a “Deno detected” branch early**:
   - Detect Deno execution via `process.env.DENO_VERSION` or `globalThis.Deno` (careful: if running under Node, it won’t exist).
   - Also consider “Deno project” detection via presence of `deno.json/deno.jsonc/deno.lock`.

2) **Add a Deno package manager “type” or at least a Deno-aware mode**:
   - Your docstring says return values are `'npm', 'pnpm', 'bun', 'yarn1', 'yarn2'`.
   - To truly support “Deno tasks” as first-class, you probably need a new `PackageManagerName.DENO` (and then implement `JsPackageManager` for it), OR a more general concept like “runtime runner” separate from “package manager”.
   - If you *don’t* add `deno`, you can still make Deno work by always choosing `npm` and ensuring “install / add / init” flows don’t require global npm binaries in a way that breaks under Deno. But you’ll hit limits quickly (especially for “run scripts” semantics).

3) **Stop throwing when no Node lockfile exists (Deno projects)**:
   - Today, if no lockfile and `hasNPM(cwd)` is false, it throws.
   - For Deno projects, it should not throw just because npm isn’t installed globally; the user may intend `deno task` or `deno run`.
   - At minimum: if Deno is detected, prefer returning `npm` (for installs) or `deno` (for running tasks), rather than throwing.

4) **Update “infer from user agent” to understand Deno**:
   - Deno sets different env vars than npm/yarn. The current `inferPackageManagerFromUserAgent()` likely won’t see `deno run npm:storybook...` as npm/yarn/pnpm.
   - You’ll want logic like: if the process appears to be launched via Deno, treat it as Deno (or treat it as npm-under-deno for install steps).

---

## 3) Add a Deno-aware implementation for “run/install” operations

Even if `getPackageManagerType` returns something, Storybook still needs to:
- install dependencies
- add packages
- run scripts / execute binaries
- possibly write config files

For Deno support you need a clear policy for each operation:

### Installs / adding deps
- In npm-compat mode, dependencies still come from npm, so “install” might still be `npm install` (or `pnpm`, etc.) **if those are present**.
- But a Deno-first project may not want `node_modules` at all. Deno can use npm packages without `node_modules` depending on configuration/version, but tooling expectations vary.
- So you need either:
  - an explicit “Deno mode uses npm install anyway”, documented, or
  - a “deno add npm:pkg” strategy (Deno has `deno add`), which is a different dependency model than package.json.

### Running Storybook
- If the user wants `deno task storybook`, then Storybook must generate/update `deno.json` tasks (or at least not break if tasks exist).
- Alternatively, generate npm scripts and recommend running via Node; but that contradicts the stated goal.

In practice, this is why it’s cleaner to model **runtime runner** separately from **package manager**:
- package manager: npm/pnpm/yarn/bun/deno-add
- runner: node/deno/bun

---

## 4) Audit Node-specific assumptions in the CLI path

Even if Deno can run many Node APIs, typical breakpoints are:
- filesystem/path edge cases
- spawning processes (`child_process`) and shell quoting differences
- reliance on `npx` behavior
- reading `process.env.npm_config_user_agent` or similar variables
- assuming `package.json` exists

To support Fresh/Deno projects, you’ll need:
- graceful behavior when **package.json is absent**
- new project-root detection logic that doesn’t assume npm layout
- feature gating: “init” may need a different template for Deno/Fresh

---

## 5) Documentation + UX changes (important for acceptance)

To make this support “real” (not just “it doesn’t crash”), you should add:
- a documented “Deno support” section: supported commands, prerequisites, limitations
- clear guidance for Fresh users (ties into denoland/fresh/discussions/542)
- CI coverage: one minimal Deno project fixture that runs `init` + `storybook` (or at least the CLI entrypoints)

---

## What I would implement first (smallest path to value)

1) **Detect Deno** (runtime and/or project files).
2) **Update `getPackageManagerType`** so Deno doesn’t end up in the “no lockfile => throw” path:
   - if Deno detected and no known lockfile: return `npm` (or a new `deno` value).
3) **Teach `inferPackageManagerFromUserAgent()` about Deno launches**.
4) **Add a basic “Deno runner” path for executing Storybook** (even if installs still use npm).
5) Add a minimal doc + a smoke test.

---

## One clarification that determines the architecture
When you say “support Deno”, do you mean:

A) “Allow running Storybook CLI via `deno run npm:storybook@latest ...` (npm dependencies), but still install via npm/pnpm/yarn”, **or**
B) “Deno-first dependency management (`deno.json` + `deno add`) with no Node package manager required”?

If you answer A vs B, I can outline the exact code touchpoints in Storybook’s `js-package-manager` layer and what new enum/abstractions are needed.