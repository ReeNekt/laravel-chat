# ReeNekt/laravel-chat
Simple chat application based on Laravel framework, Laravel Echo Server and Socket.IO
## Installing
1. Clone this repository `git clone https://github.com/ReeNekt/laravel-chat.git <project folder>`
2. Install redis server `sudo apt install redis-server`
3. Change to the project directory `cd <project folder>`
4. Install composer dependencies `composer install`
5. Install npm modules
*Using NPM:*
`npm install`
*Using yarn:*
`yarn`
6. Copy `.env.example` to `.env` and edit if you need
7. If you haven't installed Laravel Echo Server use `sudo npm install -g laravel-echo-server`
8. Init Laravel Echo: `laravel-echo-server init`
+ *Options*
   + development mode - yes (Recommended)
   + port 6001 (default) (Recommended)
   + database - redis (**Necessarily**)
   + host - localhost (default) (Recommended)
   + HTTP/HTTPS - HTTP (Recommended)
   + HTTP API - no
   + cross domain access - no
>*You always can edit this options in config file.
If you select a port other than 6001, change the line in the resources / js / bootstrap.js file and then use* `npm run dev`
```js
window.Echo = new Echo({
    broadcaster: 'socket.io',
    host: window.location.hostname + ':6001' //change 6001 to your chosen port
});
```
9. Start Laravel Echo Server and Laravel Queue
`laravel-echo-server start`
`php artisan queue:work`

#### Checklist
- [x] Public chat (works with two and more browser windows, without authorization)
- [ ] Private chats

If you have problem, try this command in `<froject folder>`: `php artisan config:cache`
