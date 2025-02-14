# Chatbot-For-FAQs
Chatbot For FAQs
#include <iostream>
#include <map>
#include <string>
#include <algorithm> 

using namespace std;

// Function to convert input to lowercase for case-insensitive comparison
string toLowerCase(string str) {
    transform(str.begin(), str.end(), str.begin(), ::tolower);
    return str;
}

int main() {
    // Predefined FAQs and their answers
    map<string, string> faq;
    faq["what is your name?"] = "I am a chatbot designed to answer FAQs.";
    faq["how does this chatbot work?"] = "I use keyword matching to provide answers.";
    faq["who created you?"] = "I was created as a C++ project for FAQ answering.";
    faq["what is AI?"] = "AI stands for Artificial Intelligence, which enables machines to simulate human intelligence.";
    faq["how can i contact support?"] = "You can contact support via email at support@example.com.";
    
    string userInput;
    
    cout << "Welcome to the FAQ Chatbot! Type 'exit' to quit.\n\n";
    while (true) {
        cout << "You: ";
        getline(cin, userInput);
        
        // Convert input to lowercase
        string lowerInput = toLowerCase(userInput);
        
        if (lowerInput == "exit") {
            cout << "Chatbot: Goodbye! Have a great day!\n";
            break;
        }
        
        // Search for the question in the FAQ map
        if (faq.find(lowerInput) != faq.end()) {
            cout << "Chatbot: " << faq[lowerInput] << "\n";
        } else {
            cout << "Chatbot: I'm sorry, I don't have an answer for that. Try asking something else.\n";
        }
    }
    
    return 0;
}
