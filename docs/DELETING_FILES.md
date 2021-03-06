# Deleting Files

With `rhc` you can delete what you already created with [`create` commands](./CREATING_FILES.md).

The following points shows how to deal with deleting your files with the `delete` command.

## Components

1. To delete a component simply run:

```sh
rhc delete -c <component-name>
```

- This will delete the component with the given name `<component-name>` under the `src/components/` folder.

- If the component does not exist, `rhc` will prompt the following:

```sh
src/components/<component-name>/ does not exist
```

2. To delete multiple components run:

```sh
rhc delete -c <component-name-1> <component-name-2> ...
```

- This will delete only the existed components with the given inputs that resides under the `src/components/` folder.

3. To delete one or multiple components that resides in a specific path under the `src/components/` folder, you can run:

```sh
rhc delete -c <component-name-1> <component-name-2> ... -f <folder-path>
```

- This will delete only the existed components with the given inputs that resides under the `src/components/<folder-path>/` folder.

## Pages

1. To delete a page simply run:

```sh
rhc delete -p <page-name>
```

- This will delete the page with the given name `<page-name>` under the `src/pages/` folder.

- If the page does not exist, `rhc` will prompt the following:

```sh
src/pages/<page-name>/ does not exist
```

2. To delete multiple pages run:

```sh
rhc delete -p <page-name-1> <page-name-2> ...
```

- This will delete only the existed pages with the given inputs that resides under the `src/pages/` folder.

3. To delete one or multiple pages that resides in a specific path under the `src/pages/` folder, you can run:

```sh
rhc delete -p <page-name-1> <page-name-2> ... -f <folder-path>
```

- This will delete only the existed pages with the given inputs that resides under the `src/pages/<folder-path>/` folder.

## Redux

- To delete a redux implementation run:

```sh
rhc delete -r
```

- This will delete the `redux` folder under `src/` with all of its files and subfolders.

- If `redux` does not exist, `rhc` will prompt:

```sh
src/redux/ does not exist
```

- ### Reducers

1 - To delete a reducer run:

```sh
rhc delete --reducer <reducer-name>
```

- This will delete the existed reducer under `src/redux/reducer/` folder, if not `rhc` will prompt the following:

```sh
./src/redux/reducers/<reducer-name>/ does not exist
```

- It will also update the `index.js` file under `src/redux/reducer/` folder to remove it from the import list as well as from the `combineReducers` function.

2 - You can even delete multiple reducers at once:

```sh
rhc delete --reducer <reducer-name-1> <reducer-name-2> ...
```

3 - To delete all reducers run:

```sh
rhc delete --reducer
```

- ### Actions

1 - To delete an action run:

```sh
rhc delete --action <reducer-name> <action-name>
```

- If the reducer does not exist, `rhc` will prompt the following:

```sh
./src/redux/actions/<reducer-name>/ does not exist
```

- It will also update the necessary files to remove the action from the reducer. And in case of TypeScript projects it will remove the action type in the `src/redux/index.ts`.

2 - You can even delete multiple actions for a specific reducer at once:

```sh
rhc delete --action <reducer-name> <action-name-1> <action-name-2> ...
```

3 - To delete all actions for a specific reducer run:

```sh
rhc delete --action <reducer-name>
```

## Configuration

- To delete a configuration file run:

```sh
rhc delete --config
```

- This will delete the `rhc.config.json` file at the root of the project.

- If `rhc.config.json` does not exist, `rhc` will prompt:

```sh
rhc.config.json does not exist
```
