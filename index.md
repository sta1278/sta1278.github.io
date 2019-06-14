# The website of STA.

### What is the STA, Spy Technology Association?
<i>It is a association Eric Curnow created.</i>
This association lets you program(especially Python) and do spy things.
<b>But we're just kids, why so serious?</b>
These are some Python codes:
'''python
class Fraction:
    def __init__(self, numerator, denominator):
        if type(numerator) == str:
            raise self.FractionNumeratorIsString("Numerator can't be string!")
        elif type(denominator) == str:
            raise self.FractionDenominatorIsString("Denominator can't be string!")
        if denominator == 0:
            raise self.FractionFloorDivisionError("Denominator can't be zero!")
        if numerator < denominator:
            self.properFraction = True
        else:
            self.properFraction = False

        self.rawNumerator = numerator
        self.rawDenominator = denominator
        self.rawValue = str(numerator) + '/' + str(denominator)

        self.numerator, self.denominator = self.simplify(numerator, denominator)
        self.value = str(self.numerator) + '/' + str(self.denominator)

        self.trueValue = numerator / denominator

    class FractionFloorDivisionError(Exception):pass
    class FractionDenominatorIsZeroError(Exception):pass
    class FractionNumeratorIsString(Exception):pass
    class FractionDenominatorIsString(Exception):pass

    def z1(self, n1, n2):
        result = 0
        for i in range(1, n2+1):
            if i * n1 % n2 == 0:
                result = i*n1
                break
        return result

    def z2(self, n1, n2):
        l = []
        for i in range(1, n1+1):
            if n1%i == 0 and n2%i == 0:
                l.append(i)
        if l == []:
            l.append(1)
        return max(l)

    def simplify(self, numerator, denominator):
        z2n = self.z2(numerator, denominator)
        numerator = numerator // z2n
        denominator = denominator // z2n
        return numerator, denominator

    def numden(self, another_fraction, needAllDenominator=True):
        f1 = another_fraction
        allDenominator = self.z1(self.denominator, f1.denominator)

        newselfNumerator = self.numerator * (allDenominator // self.denominator)
        newAnotherFractionNumerator = f1.numerator * (allDenominator // f1.denominator)

        if needAllDenominator:
            return newselfNumerator, newAnotherFractionNumerator, allDenominator
        else:
            return newselfNumerator, newAnotherFractionNumerator

    def __str__(self):
        return self.value

    def __repr__(self):
        return self.value

    def __add__(self, another_fraction):
        if type(another_fraction) == str:
            return self.value

        f1 = another_fraction
        newselfNumerator, newAnotherFractionNumerator, allDenominator = self.numden(f1)
        newfractiontuple = self.simplify(newselfNumerator + newAnotherFractionNumerator, allDenominator)

        newFraction = str(newfractiontuple[0]) + '/' + str(newfractiontuple[1])
        return newFraction

    def __sub__(self, another_fraction):
        if type(another_fraction) == str:
            return self.value

        f1 = another_fraction
        newselfNumerator, newAnotherFractionNumerator, allDenominator = self.numden(f1)
        newfractiontuple = self.simplify(newselfNumerator + newAnotherFractionNumerator, allDenominator)

        newFraction = str(newfractiontuple[0]) + '/' + str(newfractiontuple[1])
        return newFraction

    def __mul__(self, another_fraction):
        f1 = another_fraction
        numerator = self.numerator * f1.numerator
        demominator = self.denominator * f1.denominator
        newfractiontuple = self.simplify(numerator, demominator)
        newFraction = str(newfractiontuple[0]) + '/' + str(newfractiontuple[1])
        return newFraction

    def __truediv__(self, another_fraction):
        f1 = another_fraction
        numerator = self.numerator * f1.denominator
        demominator = self.denominator * f1.numerator
        newfractiontuple = self.simplify(numerator, demominator)
        newFraction = str(newfractiontuple[0]) + '/' + str(newfractiontuple[1])
        return newFraction

    def __floordiv__(self, another_fraction):
        raise self.FractionFloorDivisionError("You can't floor division a fraction! (Unless you write the method by yourself!)")

    def __lt__(self, another_fraction):
        f1 = another_fraction
        newselfNumerator, newAnotherFractionNumerator = self.numden(f1, False)

        return newselfNumerator < newAnotherFractionNumerator

    def __le__(self, another_fraction):
        f1 = another_fraction
        newselfNumerator, newAnotherFractionNumerator = self.numden(f1, False)

        return newselfNumerator <= newAnotherFractionNumerator

    def __eq__(self, another_fraction):
        f1 = another_fraction
        newselfNumerator, newAnotherFractionNumerator = self.numden(f1, False)

        return newselfNumerator == newAnotherFractionNumerator

    def __ne__(self, another_fraction):
        f1 = another_fraction
        newselfNumerator, newAnotherFractionNumerator = self.numden(f1, False)

        return newselfNumerator != newAnotherFractionNumerator

    def __gt__(self, another_fraction):
        f1 = another_fraction
        newselfNumerator, newAnotherFractionNumerator = self.numden(f1, False)

        return newselfNumerator > newAnotherFractionNumerator

    def __ge__(self, another_fraction):
        f1 = another_fraction
        newselfNumerator, newAnotherFractionNumerator = self.numden(f1, False)

        return newselfNumerator >= newAnotherFractionNumerator
 '''
  See?
