# Gather and Present Health-data

Data about a person's health and fitness comes from different sources:

- Wearables like watches
- Clinical / lab reports
- Imaging

They have different formats:

- Streaming data
- Charts / statistics
- ECG
- Pictures
- Videos
- Text / prescriptions

Users like to consume this data using different media:

- PDF reports (sent over e-mail)
- HTML reports (accessed via web)
- Mobile apps
- Voice assistants
- Reminder systems

## The product

We need a software solution to get the data
in the required format on the desired media.

One way is to code it all in the `main` function.

```C
void main() {
    //read the inputs
    switch(type_of_input) {
        case STREAM:
            switch(format) {
                ...
                switch(media_desired) {
                    case PDF:
                        ...
                }
            }
    }
}
```

This has obvious drawbacks of complexity and inflexibility.
A developer would need to copy the entire code, when a new customer
has a new data-source.

## The task

Cut the implementation into parts.
State the responsibility of each part.
