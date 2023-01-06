### Retrieve and display information
To retrieve and display information about users using the Twitter API in C#, you will need to follow these steps:

1. Set up a project in the Twitter Developer Dashboard and obtain a set of API keys and access tokens.
2. Install the Twitter API client library for C#. You can do this using the NuGet package manager in Visual Studio or by downloading the library from nuget.org.
3. Create a new C# console application and include the necessary using statements for the Twitter API client library.
4. In your application, create a new TwitterService object and set the API keys and access tokens that you obtained in step 1.
5. Call the Users.Lookup method on the TwitterService object, passing in a comma-separated list of user IDs or screen names as a parameter. This will retrieve the user objects for the specified users.
5. Iterate through the list of User objects that are returned and display the desired information for each user, such as the name, screen name, location, and profile image URL.

Here is some sample code that demonstrates how to do this:

```csharp
using Tweetinvi;
using Tweetinvi.Models;

namespace TwitterAPI
{
    class Program
    {
        static void Main(string[] args)
        {
            // Set the API keys and access tokens.
            Auth.SetUserCredentials("API_KEY", "API_SECRET", "ACCESS_TOKEN", "ACCESS_TOKEN_SECRET");

            // Retrieve the user objects.
            // var users = User.Lookup("USER_ID_1,USER_ID_2,USER_ID_3"); // Replace "USER_ID_1,USER_ID_2,USER_ID_3" with a comma-separated list of user IDs.
            var users = User.Lookup("SCREEN_NAME_1,SCREEN_NAME_2,SCREEN_NAME_3"); // Replace "SCREEN_NAME_1,SCREEN_NAME_2,SCREEN_NAME_3" with a comma-separated list of screen names.

            // Iterate through the list of users and display the desired information.
            foreach (var user in users)
            {
                Console.WriteLine("Name: " + user.Name);
                Console.WriteLine("Username: " + user.ScreenName);
                Console.WriteLine("Location: " + user.Location);
                Console.WriteLine("Profile image URL: " + user.ProfileImageUrl);
                Console.WriteLine("-------------------");
            }
        }
    }
}
```

This code will retrieve the user objects for the specified users and display the name, screen name, location, and profile image URL for each user. You can customize the code to display any other desired information about the users.