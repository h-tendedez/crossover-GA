% Pass in parents, chromosomes and population.
function [newGen] = crossOver(parent, chrome, population)

% Calculate couples
numberOfCouples = population/2;

% Counter
k = 1;

% Store New Generation
newGen = zeros(population,30);

% Cross Over Probability 
crossOverProbability = 0.50;

 % Random Number to decide
decider = rand(1);

for couple = 1:numberOfCouples
    
        % Choose the couple of parents to make children
        parent1 = couple*2 - 1;
        parent2 = couple*2;
             
        % Check if the decider is smaller than probability
        % if it is, cross over
        if decider <= crossOverProbability
            
             % Length of Chromosome
             chromLength = 30;

             % Find the location of the parents to use full chromosomes 
             parentChrome1 = parentAnts(parent1, :);
             parentChrome2 = parentAnts(parent2, :);
    
            % Random cross over points for two point cross over 
            % Number between 1 and length/2 - 1
            %If firstCrossOverPoint = i, then keep ith element of first chromosome
            firstCrossOverPoint = randi(chromLength/2 - 1);     
            % Number between length/2 and length
            secondCrossOverPoint = chromLength/2 - 1 + randi(chromLength/2);         
    
            % Creating pair of children from parents 
            child1 = [parentChrome1(1:firstCrossOverPoint) parentChrome2(firstCrossOverPoint+1:secondCrossOverPoint) parentChrome1(secondCrossOverPoint+1:chromLength)];
            child2 = [parentChrome2(1:firstCrossOverPoint) parentChrome1(firstCrossOverPoint+1:secondCrossOverPoint) parentChrome2(secondCrossOverPoint+1:chromLength)];
        
            % Saving children into a new generation
            newGen(k,:) = child1;
            k = k + 1;
            newGen(k,:) = child2;
            k = k + 1;
            
            %disp('CROSS OVER ')

        end
       
       % If not, just store parents in the new generation.
       if decider >= crossOverProbability
           
          parentChrome1 = parentAnts(parent1, :);
          parentChrome2 = parentAnts(parent2, :);
        
            newGen(k,:) = parentChrome1;
            k = k + 1;
            newGen(k,:) = parentChrome2;
            k = k + 1;
            
            %disp(' NO CROSS OVER ')
       end
       
end
    
