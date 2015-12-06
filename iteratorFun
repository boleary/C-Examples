//
//  main.cpp
//  iterator
//
//  Created by Brian O'Leary on 12/5/15.
//  Copyright © 2015 Brian O'Leary. All rights reserved.
//

#include "Header.h"
#include <map>
#include <vector>
#include <iostream>

using namespace std;

int main(int argc, const char * argv[]) {
    // insert code here...
    returnItems();
    return 0;
}

void returnItems(){
    typedef map<int,vector<int>>::const_iterator cmitii;
    typedef vector<int>::const_iterator cviti;
    map<int,vector<int>> locations;
    map<int,vector<int>> tags;
    
    static const int myData[][2] =
    {
        {1,2},
        {2,3},
        {3,4},
        {4,5},
        {5,6},
        {5,7},
        {6,7}
    };
    
    for(int i=0; i<7; i++)
    {
        cmitii itl = locations.find(myData[i][0]);
        if (  itl == locations.end())
        {
            vector<int> tag = {myData[i][1]};
            locations.insert(pair<int,vector<int>>(myData[i][0],tag));
        }
        else
        {
            locations[myData[i][0]].push_back(myData[i][1]);
        }
        
        cmitii itt = tags.find(myData[i][1]);
        if (  itt == tags.end())
        {
            vector<int> location = {myData[i][0]};
            tags.insert(pair<int,vector<int>>(myData[i][1],location));
        }
        else
        {
            tags[myData[i][1]].push_back(myData[i][0]);
        }
        
    }
    
    for (cmitii itl = locations.begin(); itl != locations.end(); itl++){
        for (cviti itv=locations[itl->first].begin(); itv != locations[itl->first].end(); itv++){
            cout << itl->first << " : " << *itv << endl;
        }
    }
    
    cout << "\n" << endl;
    
    for (cmitii itt = tags.begin(); itt != tags.end(); itt++){
        for (cviti itv=tags[itt->first].begin(); itv != tags[itt->first].end(); itv++){
            cout << itt->first << " : " << *itv << endl;
        }
    }
}


