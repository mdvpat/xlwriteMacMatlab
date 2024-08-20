The function xlwrite has similar syntax and inputs as MatLAB's xlswrite.
It also can write 3-d arrays (xlswrite can't), of cell and double type. To simplify the idea : we forward Matlab data to be exported to a Java function which in turn writes the data to excel.

Note that data to be exported is converted to cell then to java String array.

This workaround is a real working solution, it may need further refinements :
- manage Java heap space, as Java heap memory saturates for large arrays exported many times.
- format dates and strings, as all numbers appear as text in Excel.

Matlab's decimal separator is '.' : in order to be able to work with exported data, users of this solution will have to change Mac preferences regarding the decimal separator (should be ".").
To do so you need to go to System Preferences > International > Formats and click on Customize button in number zone, then type '.' in the field required.
This solution works under Windows.

Test_xlwrite.m contains an example.
