@startuml
|User|
start
:Open application;

|System|
:AppComponent loads;

|User|
:Enter username & password;
:Click Login;

|System|
:Validate form;
:Call Auth API;

if (Credentials valid?) then (Yes)
  :Store token & roles;
  :Router navigation;
  :AuthGuard check;
  :RoleGuard check;
  :Load role dashboard;

  |User|
  :Select menu option;

  |System|
  :Open selected component;

  |User|
  :Use feature page;
  :Click logout;

  |System|
  :Clear token (logout);

else (No)
  |User|
  :Show error message;
endif

|User|
stop
@enduml
