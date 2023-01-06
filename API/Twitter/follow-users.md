### Follow and unfollow users

To follow or unfollow users from your application using the Twitter API in C#, you will need to follow these steps:

1. Set up a project in the Twitter Developer Dashboard and obtain a set of API keys and access tokens.
2. Install the Twitter API client library for C#. You can do this using the NuGet package manager in Visual Studio or by downloading the library from nuget.org.
3. Create a new C# console application and include the necessary using statements for the Twitter API client library.
4. In your application, create a new TwitterService object and set the API keys and access tokens that you obtained in step 1.
5. To follow a user, call the Friendships.Create method on the TwitterService object, passing in the user's screen name or user ID as a parameter.
6. To unfollow a user, call the Friendships.Destroy method on the TwitterService object, passing in the user's screen name or user ID as a parameter.

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

            // Follow a user.
            // var result = Friendships.CreateFriendship("USERNAME"); // Replace "USERNAME" with the desired user's screen name.
            // var result = Friendships.CreateFriendship(USER_ID); // Replace "USER_ID" with the desired user's ID.

            // Unfollow a user.
            // var result = Friendships.DestroyFriendship("USERNAME"); // Replace "USERNAME" with the desired user's screen name.
            // var result = Friendships.DestroyFriendship(USER_ID); // Replace "USER_ID" with the desired user's ID.

            if (result)
            {
                Console.WriteLine("Operation successful!");
            }
            else
            {
                Console.WriteLine("Error performing operation.");
            }
        }
    }
}
```

This code will follow or unfollow the specified user, depending on which method you call. The result of the operation will be displayed in the console.