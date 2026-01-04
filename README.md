
# ircalculator

Implements the iRating calculator formula used in https://github.com/SIMRacingApps/SIMRacingApps/files/3617438/iRacing.SOF.iRating.Calculator.v1_1.xlsx to estimate final ratings giving the results. Its also based on https://github.com/Turbo87/irating-rs.

# Install

    pip install irating-ircalculator

# Example
    from ircalculator import IRatingCalculator, IRatingResult
    
    # results of the race in order (final positions)
    results = [
            #             Driver       ir        driver
            #             Name         at start  started
            IRatingResult("Driver 1",  8653,     True),
            IRatingResult("Driver 2",  7356,     True),
            IRatingResult("Driver 3",  8230,     True),
            IRatingResult("Driver 4",  4398,     True),
            IRatingResult("Driver 5",  3250,     True),
            IRatingResult("Driver 6",  1782,     True),
            IRatingResult("Driver 8",  8362,     False),
            IRatingResult("Driver 9",  6729,     False),
    ]
    
    newRatings = IRatingCalculator().calculate(results)
    # calculate returns an array with new iratings in order
    print(newRatings)
    # each intial IRatingResult has now an calculatedIr property with their calculated values
    for result in results:
        print(result)

