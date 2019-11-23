Bugs List:

1. Error decoding message threads from JSON data: valueNotFound(Swift.UnkeyedDecodingContainer, Swift.DecodingError.Context(codingPath: [], debugDescription: "Cannot get unkeyed decoding container -- found null value instead.", underlyingError: nil))

Potential solutions:
Check that the coding keys are accurate. Check that the decoding is happening in the correct container. Check that the data task is being called

Changes from previous commit seem to have worked. Didn't get any error messages after I created an initial thread.

Solution:
Fixed the key to be 'text' instead of 'messageText'
Decoded as a dictionary of [String: MessageThread] instead of just and array of [MessageThread]

2. Error creating new threads

Potential solutions:
Check the keys are accurate. Check that the data task is being called

Solution:
Needed to call .resume() on the dataTask

3. Sending messages does not work and screen is not being dismissed

Potential solutions:
Check that the segues between controllers are correct. Check that dismiss() is being called after sending. Check that a network call is being made to post the message

Solution:
Corrected spelling error in the prepare method 
Popped the view controller off the navigation stack