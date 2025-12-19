x = linspace(100, 200);

A_values = [1, 0.5, 0.25, 0.125];
ax = gca;


%plot top hat uniform function

uniform = zeros(size(x)); % Initialize the uniform function
uniform(x >= 125 & x <= 175) = 2; % Define the uniform function between x = 2 and x = 8
% Plot the uniform function
plot(x, uniform,"LineWidth",4);
ylabel('Function Value', FontSize=24);
xlabel('$z$',"Interpreter", "latex", FontSize=24);


hold on
for val = [10 5 2.5 1]
    y_n = tanh((x-125)/val) - tanh((x-175)/val);
    plot(x, y_n, "LineWidth", 2);
    ylim ([-0.1 2.1])
    fontsize(20,"points")

    
    hold on % Keep the first plot active
end
title("Convergence to the Smoothed Rectangular Forcing Profile By Varying tanh Parameter '\delta'",  FontSize=18);

hold off % Release the hold

legend('Uniform', '\delta=10', "\delta=5", "\delta=2.5", "\delta=1", Location="south",  FontSize=15);
grid on;
