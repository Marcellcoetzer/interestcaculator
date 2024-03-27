# interestcaculator
public class InterestCalculator {

    // Method to calculate simple interest
    public double calculateSimpleInterest(double principalAmount, double interestRate, double timePeriod) {
        // Simple interest formula: (principal_amount * interest_rate * time_period) / 100
        return (principalAmount * interestRate * timePeriod) / 100;
    }

    // Overloaded method to calculate simple interest with default time period of 1 year
    public double calculateSimpleInterest(double principalAmount, double interestRate) {
        // Default time period is 1 year
        double timePeriod = 1;
        return calculateSimpleInterest(principalAmount, interestRate, timePeriod);
    }

    // Method to calculate compound interest
    public double calculateCompoundInterest(double principalAmount, double interestRate,
                                            double timePeriod, int frequencyOfCompounding) {
        // Compound interest formula: principal_amount * (1 + interest_rate/frequency_of_compounding) ^ (frequency_of_compounding * time_period) - principal_amount
        double compoundInterest = principalAmount * (Math.pow(1 + interestRate / frequencyOfCompounding, frequencyOfCompounding * timePeriod)) - principalAmount;
        return compoundInterest;
    }

    // Main method to demonstrate the usage of each method
    public static void main(String[] args) {
        // Creating an instance of InterestCalculator
        InterestCalculator calculator = new InterestCalculator();

        // Calculating simple interest with provided parameters
        double simpleInterest = calculator.calculateSimpleInterest(1000, 5, 2);
        System.out.println("Simple Interest: " + simpleInterest);

        // Calculating simple interest with default time period
        double defaultSimpleInterest = calculator.calculateSimpleInterest(1000, 5);
        System.out.println("Simple Interest (Default Time Period): " + defaultSimpleInterest);

        // Calculating compound interest
        double compoundInterest = calculator.calculateCompoundInterest(1000, 5, 2, 4);
        System.out.println("Compound Interest: " + compoundInterest);
    }
}
