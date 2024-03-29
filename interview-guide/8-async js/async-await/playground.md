# async-await example

```javascript
function getUsers() {
  return new Promise((resolve, reject) => {
    console.log('hi', resolve, reject);
    setTimeout(() => {
      console.log('getting users');
      resolve([
        { id: 1, name: 'Naruto' },
        { id: 2, name: 'Sasuke' },
      ]);
    }, 1000);
  });
}

function getRepos() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      console.log('getting repos');
      resolve([
        { id: 1, name: 'Naruto repo1', userId: 1 },
        { id: 2, name: 'Naruto repo2', userId: 1 },
        { id: 3, name: 'Sasuke repo1', userId: 2 },
        { id: 4, name: 'Sasuke repo2', userId: 2 },
      ]);
    }, 1000);
  });
}

function getCommits() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      console.log('getting commits');
      resolve([
        { id: 1, name: 'Naruto commit1', repoId: 1 },
        { id: 2, name: 'Naruto commit2', repoId: 1 },
        { id: 3, name: 'Sasuke commit1', repoId: 1 },
        { id: 4, name: 'Sasuke commit2', repoId: 1 },
      ]);
    }, 1000);
  });
}

async function getAllData() {
  const users = await getUsers();
  console.log('users are ', users);
  const repos = await getRepos();
  console.log('repos are ', repos);
  const commits = await getCommits();
  console.log('commits are ', commits);
}

getAllData();
```
