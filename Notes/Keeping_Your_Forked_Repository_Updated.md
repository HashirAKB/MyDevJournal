# Keeping Your Forked Repository Updated

## Adding the Original Repository as a Remote

After forking a repository to your local machine, you might want to keep your forked repository updated with the latest changes from the original repository. To do this, you need to add the original repository as a remote. Here's how:

1. Navigate to the directory of your local repository in your terminal.
2. Add the original repository as a remote. You can name this remote whatever you want, but typically people call it `upstream`. Replace `original_owner` and `original_repo` with the username and repository name of the original repository.

   ```
   git remote add upstream https://github.com/original_owner/original_repo.git
   ```

## Fetching All Branches from the Original Repository

Once you've added the original repository as a remote, you can fetch all the branches from the original repository:

```
git fetch upstream
```

## Merging Changes from the Original Repository

To merge the changes from the original repository into your local repository, first checkout to the branch you want to update (usually `master` or `main`), and then merge the corresponding branch from the `upstream`:

```
git checkout master
git merge upstream/master
```

Remember to replace `master` with the appropriate branch name if necessary.

By following these steps, you can keep your forked repository updated with the latest changes from the original repository.