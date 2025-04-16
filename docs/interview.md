1. Do you have Node.js installed? If not, how do you install it?
   - `Windows Subsystem for Linux (WSL)` (if on Windows)
     - [Install WSL](https://docs.microsoft.com/en-us/windows/wsl/install])
   - `Node.js`
     - [Install Volta](https://volta.sh/)
     - `volta install node@22`
2. How would you initialize a new TypeScript Express app?
   - `npx express-generator-typescript`
3. Initialize git in the project & make the first commit.
   - `git init`
4. How would you go about understanding this Express app?
   - run `npm ci` to install dependencies
   - Why not `npm install`?
     - `npm ci` is faster and more reliable for CI/CD pipelines.
     - It installs the exact versions of dependencies listed in `package-lock.json`.
   - See what the npm scripts are and what they do.
   - Find how to start the app locally
   - What port does it run on?
   - What routes are available?
5. How would you manually test the available routes?
   - Postman
   - curl (may need to install `jq` for pretty printing)
     - `export URL=http://localhost:3000/api/users`
     - `export CT="Content-Type: application/json"`
     - `curl "$URL/all" -v | jq`
     - `curl -H "$CT" -X POST $URL/add -d '{"user":{"id":0,"name":"Ben","email":"ben@symetra.com","created":"2025"}}' -v`
     - `curl -H "CT" -X PUT $URL/update -d '{"user":{"id":"","email": "ben.formantes@symetra.com"}}' -v | jq`
6. Would you say the `User` resource is RESTful. How would you make it RESTful?
   - `GET /api/users/all` should be `GET /api/users`
   - `POST /api/users/add` should be `POST /api/users`
   - `PUT /api/users/update` should be `PUT /api/users/:id`
   - `DELETE /api/users/delete` should be `DELETE /api/users/:id`
