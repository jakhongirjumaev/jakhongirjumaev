

- 👋 Hi, I’m @jakhongirjumaev
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
jakhongirjumaev/jakhongirjumaev is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
// Password generator
#include <iostream>
#include <string>
#include <algorithm>
#include <sstream>  

std::string password_gen() {
  std::string result;
  while (!any_of(result.begin(), result.end(), ::islower) ||
         !any_of(result.begin(), result.end(), ::isupper) ||
         !any_of(result.begin(), result.end(), ::isdigit)) {
    std::stringstream ss;
    int length = rand() % 15 + 6;
    for (int i = 0; i < length; i++) {
      unsigned randomChar = rand() % 62;
      if (randomChar < 26)
        ss << char(randomChar + 'a');
      else if (randomChar < 52)
        ss << char(randomChar - 26 + 'A');
      else if (randomChar < 62)
        ss << char(randomChar - 52 + '0');
      result = ss.str();
    }
  }
  return result;
}

using namespace std;

int main() {

    cout<<"New random password = " << password_gen();
}
