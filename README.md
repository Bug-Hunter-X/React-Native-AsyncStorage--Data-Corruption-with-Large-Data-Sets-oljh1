# React Native AsyncStorage Data Corruption Bug

This repository demonstrates a common but hard-to-debug issue in React Native applications involving AsyncStorage. When attempting to store large datasets exceeding AsyncStorage's limitations, data corruption or unexpected app crashes can occur. This often comes without clear error messages.

## Bug Description

The core problem is exceeding AsyncStorage's storage capacity.  Storing a large array of data (as demonstrated in `bug.js`) causes inconsistent behavior; sometimes data is partially saved, other times the app crashes.  The lack of informative error messages makes identification and resolution challenging.

## Solution

The solution (`bugSolution.js`) addresses this by implementing data chunking. This technique breaks down the large dataset into smaller, manageable pieces before storing them in AsyncStorage.  Each chunk is stored with a unique key, allowing for later retrieval and reassembly.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` or `yarn install`.
3. Run the application on your preferred emulator or device.  Observe the behavior when attempting to store the large dataset in `bug.js` and compare with the corrected handling in `bugSolution.js`.