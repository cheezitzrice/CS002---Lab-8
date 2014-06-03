CS002---Lab-8
=============

/* START COMMENTS AND NOTES
 Alexander Woo, Kevin Ortiz
  Lab 8
  Last Modified - June 2nd, 2014

  Design:
  INPUT:
  1. The program will request the user to input the size of the shape
     and the type of shape they want.
  2. The program will check if size is >= 1 for size. As for shape, the
     string will be checked for the appropriate characters.
  3. Pseudocode:
     cout -> Give me the size of the shape
     cin -> size
     cout -> Give me the shape
     cin -> shape
  PROCESSING:
  1. The program will read the inputs. The size will dictate the maximum
     size of the whatever shape is selected. The shape will dictate what
     shape will be outputted.
  2. Could make individual "line" drawing functions to draw out the shapes.
  3. Pseudocode:
     if (equal to shape)
           if (size)
               line-drawing function
  OUTPUT:
  1. The output will be the selected shape with size appropriate to size.
  2. It will just output the * in a shape requested.
  3. Pseudocode:
   ******** (shape drawn in asterisks)


END COMMENTS AND NOTES*/


#include <iostream>
#include <string>

using namespace std;

int main()
{
    // Declare variables.
    int size; // For size of the shape (input by user).
    string shape = " "; // For type of shape (input by user).
    int size_counter, blank_counter, star_counter; // For usage in for loops.

    // Request user input for size of shape, and type of shape
    cout << "____________________________________________\n"
         << "Please input the size of the shape you want.\n"
         << "Input size here: ";
    cin >> size;

    while (size <= 0)
    {
        cout << "____________________________________________\n"
             << "ERROR: Invalid size for shapes.\n"
             << "Please input a valid value next time.\n"
             << "Please input the size of the shape you want.\n"
             << "Input size here: ";
        cin >> size;
    }

    cout << "____________________________________________\n"
         << "Please input the type of shape you want.\n"
         << "____________________________________________\n"
         << "Please pick either TRI, DIA, UDT, or SWT.\n"
         << "TRI for standard triangle.\n"
         << "DIA for diamond.\n"
         << "UDR for up-side down triangle.\n"
         << "And SWT for side-ways triangle.\n"
         << "Please use CAPS for input.\n"
         << "____________________________________________\n"
         << "Input shape here: ";
    cin >> shape;


    while ((shape != "TRI") && (shape != "DIA") && (shape != "UDT") && (shape != "SWT"))
    {
        cout << "____________________________________________\n"
             << "ERROR: Invalid shape type.\n"
             << "Please input a valid shape next time.\n"
             << "Please input the shape you want.\n"
             << "Input shape here: ";
        cin >> shape;
    }

    // An if statement for when shape is "TRI" or a triangle.
    if (shape == "TRI")
    {
        // Output fluff.
        cout << "____________________________________________\n"
             << "You requested a triangle?\n";

        for (size_counter = 0; size_counter <= size; ++size_counter)
        {
            for (blank_counter = 0; blank_counter < (size - size_counter); ++blank_counter)
            {
                cout << " ";
            }

            for (star_counter = size_counter; star_counter <= (2 * size_counter - 1); ++star_counter)
            {
                cout << "*";
            }

            for (star_counter = 0; star_counter < (size_counter - 1); ++star_counter)
            {
                cout << "*";
            }

            cout << "\n";
        }

        // Output fluff.
        cout << "____________________________________________\n"
             << "Here is a triangle with a size of " << size <<".\n";
    }


            // An else if statement for when shape is "DIA" or a diamond.
            else if (shape == "DIA")
            {
                cout << "____________________________________________\n"
                     << "You requested a diamond?\n";

                for (size_counter = 0; size_counter <= 2 * size - 1; ++size_counter)
                {
                    for (blank_counter = 0; blank_counter <= 2 * size; ++blank_counter)
                    {
                        if (size_counter < size)
                        {
                            if ((blank_counter <= (size - size_counter)) || (blank_counter >= (size + size_counter)))
                            {
                                cout << " ";
                            }

                            else
                            {
                                cout << "*";
                            }
                        }

                        else
                        {
                            if ((blank_counter <= (size_counter - size)) || (blank_counter >= (3 * size - size_counter)))
                            {
                                cout << " ";
                            }

                            else
                            {
                                cout << "*";
                            }
                        }
                    }
                    cout << "\n";
                }

                // Output fluff.
                cout << "____________________________________________\n"
                     << "Here is a diamond with a size of " << size <<".\n";
            }

            else if (shape == "UDT")
            {
                // Output fluff.
                cout << "____________________________________________\n"
                     << "You requested a upside-down triangle?\n";

                for (size_counter = 0; size_counter <= size; ++size_counter)
                {
                    for (star_counter = 0; (star_counter < (size - size_counter)); ++star_counter)
                    {
                        cout << "*";
                    }

                    for (blank_counter = size_counter; (blank_counter <= size); ++blank_counter)
                    {
                        cout << " ";
                    }

                    cout << "\n";
                }

                // Output fluff.
                cout << "____________________________________________\n"
                     << "Here is a diamond with a size of " << size <<".\n";
            }

            // Else statement for a sideways triangle as an output.
            else // if shape == "SWT"
            {
                cout << "____________________________________________\n"
                     << "You requested a sideways triangle?\n";

                for (size_counter = 0; size_counter < size; ++size_counter)
                {
                    for (blank_counter = 0; blank_counter < size_counter; ++blank_counter)
                    {
                        cout << "*";
                    }

                    cout << "\n";
                }

                for (size_counter = size; size_counter >= 0; --size_counter)
                {
                    for (blank_counter = 0; blank_counter < size_counter; ++blank_counter)
                    {
                        cout << "*";
                    }

                    cout << "\n";
                }

                // Output fluff.
                cout << "____________________________________________\n"
                     << "Here is a sideways triangle with a size of " << size <<".\n";
            }

            // Output fluff.
            cout << "____________________________________________\n\n"
                 << "End of program.\n"
                 << "____________________________________________\n\n";

            // Return 0, end of program.
            return 0;
}





