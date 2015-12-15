BitDbBcryptAuthAdapter
======================

THIS REPOSITORY WAS FORKED FROM https://github.com/cabrilo/BitDbBcryptAuthAdapter.

IT WAS FORKED FOR THE PURPOSE OF CREATING A COMPOSER PACKAGE FOR IT.

PLEASE REFER TO THE LINK ABOVE FOR ANY FURTHER INFORMATION.

COMPOSER INSTRUCTIONS
======================
Include the following line into your composer.json require.
    "velixir/bit-db-bcrypt-auth-adapter": "dev-master"
DON'T RUN THE FOLLOWING COMMAND AS IT WOULD INSTALL THE PACKAGE INTO THE WRONG DIRECTORY.
    composer require velixir/bit-db-bcrypt-auth-adapter dev-master 

In order to install the package into the right directory, add the following line at the end of your composer.json 
"extra": {
    "installer-paths": {
      "vendor/BitDbBcryptAuthAdapter": [
        "velixir/bit-db-bcrypt-auth-adapter"
      ]
    }
}